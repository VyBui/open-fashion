Upload Model Api
============================

This feature is for user to upload their picture to Smart Fashion AI (SF) project.
The api will detect whether the image has standard pose of SF in order for further processing

In case of the image has on of the following issue:

* NO_SINGLE_PERSON
* TOO_MANY_PEOPLE
* NOT_FOLLOW_SUGGESTED_POSE
* NOT_FOLLOW_SUGGESTED_POSE

the application will return an error with the specific message accordingly to the error key.

After all, if none of the error has never occurred the API will return the follow parameter:

1) /fashion_api/upload_model_client/upload_model
Request:
{
  "personImageURL": "public/photo/model/0_1592458708091.JPG",
  "gender": "Female"
}
Response:
{
    "upload_result": [
        {
            "bodyPoints": "[(533, 487), (423, 487), (395, 671), (345, 836), (643, 492), (675, 671), (722, 836), (460, 795), (602, 795), (469, 1080), (460, 1328), (597, 1084), (602, 1328), (584, 1429), (611, 1415), (588, 1337), (478, 1415), (446, 1411), (464, 1337), (533, 340), (501, 312), (561, 308), (473, 335), (597, 326)]",
            "humanKeyPoints": "[(432, 518), (431, 544), (431, 567), (436, 595), (437, 618), (437, 639), (436, 663), (640, 520), (637, 548), (633, 570), (629, 599), (626, 620), (624, 643), (626, 666), (436, 686), (430, 707), (424, 728), (421, 745), (418, 763), (411, 785), (630, 689), (633, 708), (639, 729), (643, 746), (646, 764), (653, 784), (410, 808), (409, 834), (408, 864), (407, 888), (408, 914), (411, 939), (414, 965), (419, 992), (422, 1016), (426, 1040), (429, 1067), (524, 860), (522, 885), (529, 910), (528, 935), (525, 959), (522, 981), (517, 1003), (514, 1027), (512, 1046), (510, 1069), (652, 806), (651, 832), (650, 864), (649, 887), (648, 912), (646, 939), (642, 963), (638, 991), (634, 1017), (630, 1041), (628, 1066), (538, 860), (540, 885), (530, 909), (534, 934), (535, 959), (538, 981), (540, 1005), (541, 1031), (543, 1050), (545, 1074), (426, 1095), (422, 1118), (419, 1140), (419, 1162), (421, 1187), (425, 1210), (430, 1234), (434, 1258), (438, 1281), (441, 1306), (503, 1098), (499, 1121), (498, 1142), (495, 1164), (492, 1189), (489, 1211), (486, 1235), (483, 1257), (481, 1283), (484, 1305), (630, 1097), (635, 1120), (637, 1141), (638, 1164), (635, 1188), (631, 1211), (627, 1235), (622, 1259), (617, 1284), (616, 1307), (552, 1102), (557, 1126), (559, 1147), (560, 1170), (560, 1193), (563, 1215), (566, 1238), (571, 1260), (573, 1284), (574, 1307), (396, 471), (388, 490), (384, 511), (383, 533), (381, 553), (381, 572), (381, 593), (380, 615), (380, 636), (375, 660), (438, 529), (436, 554), (434, 576), (432, 599), (429, 624), (428, 650), (427, 674), (670, 471), (680, 490), (684, 511), (687, 532), (688, 553), (689, 572), (689, 593), (690, 616), (691, 637), (695, 660), (632, 530), (635, 554), (637, 577), (640, 599), (637, 625), (639, 652), (641, 676), (370, 678), (363, 704), (358, 728), (353, 751), (349, 773), (344, 798), (338, 822), (423, 694), (414, 719), (403, 746), (392, 770), (381, 792), (372, 812), (363, 831), (700, 678), (707, 703), (712, 728), (716, 751), (721, 775), (727, 797), (734, 822), (645, 696), (653, 721), (665, 747), (676, 771), (686, 793), (695, 812), (705, 831), (413, 460), (433, 454), (450, 448), (466, 443), (481, 435), (499, 413), (499, 391), (574, 391), (573, 413), (586, 435), (599, 444), (617, 449), (636, 455), (653, 461)]",
            "jobId": "a44bfd45-a7c8-402c-87ea-c7f75ae77a4a",
            "messageKey": "successful",
            "statusCode": 202
        }
    ]
}

2) /fashion_api/upload_model_client/get_upload_model_result_by_job_id
Request:
{
    "jobId": "a44bfd45-a7c8-402c-87ea-c7f75ae77a4a"
}
Response:
{
    "upload_result": [
        {
            "humanSkinImageURL": "private/photo/model/skin_0_1592458708091_1599115125.png",
            "backGroundImageURL": "private/photo/model/bg_0_1592458708091_1599115125.png",
            "statusCode": 200,
            "message": "successful"
        }
    ]
}


* **Prerequisite requirements**:
  :doc:`Start Openpose </system/start-open-pose>,
    TensorFlow Serving </system/start-tensorflow-serving>,
    Redis Server </system/redis-queue>`

.. toctree::
   :maxdepth: 1
   :hidden:
   :caption: Prerequisite requirements

   /system/start-open-pose
   /system/start-tensorflow-serving
   /system/redis-queue


**How to import the code**:
----------------------

- Upload upload model output until body points:
 >>> from smart_fashion_client.apis.upload_model.logic.human_pose import load_upload_model_outputs


- Get upload model skin and background images by job Id:
 >>> from smart_fashion_client.apis.upload_model.logic.human_pose import get_upload_model_result_by_job_id





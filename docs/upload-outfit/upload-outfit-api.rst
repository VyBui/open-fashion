Upload Outfit Api
============================

** Introduction**:
------------------

This feature is for shops to upload their outfit to Smart Fashion AI (SF) project for virtual exchange clothes purpose.
The api will detect whether the clothes has the standard pose of SF in order for further processing segmentation and
generate cache for faster swapping.

In case of the image has one of the following issue:

* NO_SINGLE_PERSON
* TOO_MANY_PEOPLE
* NOT_FOLLOW_SUGGESTED_POSE
* OPENPOSE ERROR

1) Upload_outfit
.. http:example:: http://localhost:5000/fashion_api/upload_outfit_client/upload_outfit
     :method: POST
     :request: {
                  "outfitImageURL": "public/photo/model/0_1592458708091.JPG",
                }
     :response: {
                  "upload_result": {
                      "outfitBodyPoints": "[(11,22), (33,44)]",
                      "outfitHumanPoints": "[(11,22), (33,44)]",
                      "outfitSegmentImageURL": "S3_link",
                      "message": "UI message",
                      "statusCode": [200, 400, 422, 500],
                      "jobId": "3b540f95-1026-44ba-b077-824309b8d2fa"
                   }
                }
2) Get_upload_outfit_by_jobId
.. http:example:: http://localhost:5000/fashion_api/upload_outfit_client/get_upload_outfit_result_by_job_id
     :method: POST
     :request: {
                        "jobId": "a44bfd45-a7c8-402c-87ea-c7f75ae77a4a"
                     }
     :response: {
                    "upload_result": [
                        {
                            "cacheDict": "private/photo/model/skin_0_1592458708091_1599115125.json",
                            "statusCode": [200. 202],
                            "message": "successful"
                        }
                    ]
                }

# ID-Document-Liveness

## Try the API
### Online Demo
  You can test the SDK using images [here](https://web.kby-ai.com).</br>  
  ![image](https://github.com/kby-ai/IDCardRecognition-Docker/assets/125717930/ff395174-d3e9-4198-bfc8-6024a8c31734)

### Documentation
https://docs.kby-ai.com/help/product/id-card-sdk

### Postman
  To test the `API`, you can use `Postman`. Here are the endpoints for testing:
  - Test with an image file: Send a `POST` request to `http://18.221.33.238:8082/idcard_recognition`.
  - Test with a `base64-encoded` image: Send a `POST` request to `http://18.221.33.238:8082/idcard_recognition_base64`.

    You can download the `Postman` collection to easily access and use these endpoints. [click here](https://github.com/kby-ai/IDCardRecognition-Docker/tree/main/postman/kby-ai-idcard.postman_collection.json)
    
    ![image](https://github.com/kby-ai/IDCardRecognition-Docker/assets/125717930/0ec93826-76d7-47a7-9065-6bd353bc79b3)


## How to run

### 1. System Requirements
  - `CPU`: `2` cores or more (Recommended: `2` cores)
  - `RAM`: `4GB` or more (Recommended: `8GB`)
  - `HDD`: `4GB` or more (Recommended: `8GB`)
  - `OS`: `Ubuntu 20.04` or later

### 2. Setup and Test
  - Clone the project:
    ```bash
    git clone https://github.com/kby-ai/IDCardRecognition-Docker.git
    ```
  - Download the model from `Google Drive`: [click here](https://drive.google.com/file/d/1fmTUG7a9IoMA8QiXR9A0xf3Cr6D5UkdC/view)
    ```bash
    cd IDCardRecognition-Docker
    
    wget --load-cookies /tmp/cookies.txt "https://docs.google.com/uc?export=download&confirm=$(wget --quiet --save-cookies /tmp/cookies.txt --keep-session-cookies --no-check-certificate 'https://docs.google.com/uc?export=download&id=1fmTUG7a9IoMA8QiXR9A0xf3Cr6D5UkdC' -O- | sed -rn 's/.*confirm=([0-9A-Za-z_]+).*/\1\n/p')&id=1fmTUG7a9IoMA8QiXR9A0xf3Cr6D5UkdC" -O data.zip && rm -rf /tmp/cookies.txt
    
    unzip data.zip
    ```
  - Build the `Docker` image:
    ```bash
    sudo docker build --pull --rm -f Dockerfile -t kby-ai-idcard:latest .
    ```
  - Run the `Docker` container:
    ```bash
    sudo docker run -v ./license.txt:/root/kby-ai-idcard/license.txt -p 8082:8080 -p 9002:9000 kby-ai-idcard:latest
    ```
  - Send us the `machine code` and then we will give you a `license key`.
  
    After that, update the `license.txt` file by overwriting the license key that you received. Then, run the `Docker` container again.
    
    ![image](https://github.com/kby-ai/IDCardRecognition-Docker/assets/125717930/deab4a80-ae99-4646-a37d-b1441cff4dde)
    
    ![image](https://github.com/kby-ai/IDCardRecognition-Docker/assets/125717930/7994cecd-05fb-42e7-a21d-986da0e2d796)

  - To test the `API`, you can use `Postman`. Here are the endpoints for testing:

    Test with an image file: Send a `POST` request to `http://{xx.xx.xx.xx}:8082/idcard_recognition`.
    
    Test with a `base64-encoded` image: Send a `POST` request to `http://{xx.xx.xx.xx}:8082/idcard_recognition_base64`.
    
    You can download the Postman collection to easily access and use these endpoints. [click here](https://github.com/kby-ai/IDCardRecognition-Docker/tree/main/postman/kby-ai-idcard.postman_collection.json)

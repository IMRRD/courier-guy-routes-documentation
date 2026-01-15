# COURIER GUY – Get Shipment Pod Image Download Urls

- You need to be logged inside of session-server to be able to test.

## Endpoint
**GET**  
`http://192.168.110.164:8823/Tracking/GetShipmentPodImageDownloadUrls?file_name={file_name}&folder={folder}`

## Purpose
Retrieves a secure, time-limited download URL for a specific Proof of Delivery (POD) image file.
This endpoint is used to access and download POD image assets stored in the system for verification and record-keeping purposes.

---

## Path Parameter
| Parameter   | Description                      |
|---------    |----------------------------------|
| `file_name` | The exact name of the POD image file to be downloaded. This value usually corresponds to the file name returned by POD or tracking-related endpoints. |
| `folder` | The folder or storage path where the POD image file is located. This parameter is required to correctly resolve the file location in the storage system. |

📥 Response Example:

❌ No response example is currently available for this endpoint with our info on platform yet or have to find out a valid value

```json
System.Exception: Error to get shipment POD image URLs: invalid folder
```

---


ℹ️ ⚠️ *Click the link below to learn more about the information related to this specific call (route).*

https://www.shiplogic.com/api-docs/get-get-signed-url-to-download-a-file
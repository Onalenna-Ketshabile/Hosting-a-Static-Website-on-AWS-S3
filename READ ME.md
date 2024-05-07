# Hosting a Static Website on AWS S3  

## 🚀 Introduction  
This project guides you through hosting a static website on AWS S3. S3 provides a simple, scalable, and cost-effective solution for static site hosting.  

---

## 📜 Steps  

### **1. Access AWS Console**  
- **Action**: Log in to your AWS account.  
- **Path**: Search for `S3` and open the service.  

### **2. Create Bucket**  
- **Action**: Click `Create Bucket`.  
- **Input**: Enter a unique bucket name.  
- **Config**: Unselect `Block All Public Access`.  

### **3. Configure Static Website Hosting**  
- **Path**: `Properties` → `Static Website Hosting`.  
- **Action**: Enable `Host a Static Website`.  
  - **Input**: Specify `index.html` as the default page.  

### **4. Add Bucket Policy for Public Access**  
- **Path**: `Permissions` → `Bucket Policy`.  
- **Input**: Use the policy below (replace `<your-bucket-name>`):  
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::<your-bucket-name>/*"
    }
  ]
}
```  

### **5. Upload Website Files**  
- **Action**: Go to the `Objects` tab and click `Upload`.  
- **Input**: Add your static files, including `index.html`.  

### **6. Test Your Website**  
- **Path**: Copy the `Bucket Website Endpoint` from `Static Website Hosting`.  
- **Verify**: Open the endpoint in your browser to see your site live.  

---

## 🎉 Conclusion  
By following these steps, you've successfully hosted a static website on AWS S3. It's fast, secure, and cost-efficient for your web projects.  

--- 
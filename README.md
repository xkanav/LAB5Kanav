# MLPR Lab 5: Grouping Faces with K-Means
Author: Kanav Nanda

Course: Machine Learning and Pattern Recognition (Spring 2026)

🎯 **What's the Goal?**
The plan for this lab was simple: spot faces in a group photo, figure out their colors (hue and saturation), and group them together using a cool machine learning algorithm called K-Means Clustering. Finally, I tested the model by throwing in a brand-new picture to see which group it fit into best!

🛠️ **How I Did It**
As an undergrad getting my hands dirty with ML, I broke the project down into a few easy steps:

- **Finding Faces:** I used OpenCV's Haar Cascade tool to scan the group photo and draw boxes around everyone's faces.
- **Grabbing Colors:** Regular RGB colors are tricky when lighting changes, so I switched to the HSV (Hue, Saturation, Value) format. I just pulled out the average Hue and Saturation for every face.
- **Clustering (The ML Part):** I asked the K-Means algorithm to split these faces into 2 distinct groups based on their color features.
- **Testing it Out:** I took a new test image, extracted its colors, and asked my trained model to drop it into the closest matching group.

📊 **What I Found**

- **Face Detection Works:** The Haar Cascade tool did a great job finding faces once I tweaked the settings to ignore background noise.
  ![Face Detection Output](./Total%20number%20of%20face%20detected%20are%2030_screenshot_15.02.2026.png)

- **Clear Groups:** Plotting the colors showed two neat groups (Cluster 0 in green, Cluster 1 in blue) based on skin tone and lighting differences.
  ![Scatter Plot of Clusters](./Dr%20Shashi%20Tharoor%20Lab%205.jpg)

- **Successful Test:** The model easily matched the new test image to the correct group based on how close its colors were to the cluster centers!
  ![Final Classification with Template](./Template%20Face_screenshot_15.02.2026.png)

💡 **My Takeaway**
K-Means is super handy for grouping data when you don't have labels to start with. But, I quickly realized that the magic really depends on the features you pick. Hue and saturation worked nicely for this lab, but for tougher real-world tasks, we'd need more advanced data.

Also, picking the right number of groups (the "K" value) is super important. If K is too high or too low, the model might overthink the noise or miss the big picture.

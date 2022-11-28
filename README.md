# Person and Forklift Detection

> This project is my internship project

 I used this Chart Diagram for development process
         ![Person-Forklift Detection Chart drawio](https://user-images.githubusercontent.com/59209205/204371290-11db1d23-6452-429e-a4cd-4704fb4eb624.png)

 EGEROBOT - isgsis
         ![egerobot_logo_01](https://user-images.githubusercontent.com/59209205/204371435-90349413-4b70-441b-af1e-e8ddf105b9fa.png)



# I updated this function code for showing the "EGEROBOT - isgsis" box.This function into the utils.plots
    def plot_one_box(x, img, color=None, label=None, line_thickness=3):
    # Plots one bounding box on image img
    tl = line_thickness or round(0.002 * (img.shape[0] + img.shape[1]) / 2) + 1  # line/font thickness
    color = color or [random.randint(0, 255) for _ in range(3)]
    c1, c2 = (int(x[0]), int(x[1])), (int(x[2]), int(x[3]))
    cv2.rectangle(img, c1, c2, color, thickness=tl, lineType=cv2.LINE_AA)
    
    # This code write the "EGEROBOT - isgsis"
    
    tf = max(tl - 1, 1)  # font thickness
    my_t_size = cv2.getTextSize("EGEROBOT - isgsis", 0, fontScale=tl / 3, thickness=tf)[0]
    my_c2 = c1[0] + my_t_size[0], c2[1] + my_t_size[1] + 3
    cv2.rectangle(img, (c1[0],c2[1]), my_c2, [0,0,0], -1, cv2.LINE_AA)
    cv2.putText(img, "EGEROBOT - isgsis", (c1[0],c2[1]+9), 0, tl / 3, [225, 255, 255], lineType=cv2.LINE_AA)
    
    # This code write the "EGEROBOT - isgsis"

    if label:
        tf = max(tl - 1, 1)  # font thickness
        t_size = cv2.getTextSize(label, 0, fontScale=tl / 3, thickness=tf)[0]
        c2 = c1[0] + t_size[0], c1[1] - t_size[1] - 3
        cv2.rectangle(img, c1, c2, color, -1, cv2.LINE_AA)  # filled
        cv2.putText(img, label, (c1[0], c1[1] - 2), 0, tl / 3, [225, 255, 255], thickness=tf, lineType=cv2.LINE_AA)
        

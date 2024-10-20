# game-auto-tool
'm not quite sure if the customers are refreshed at fixed positions. If they are, wouldn't it be possible to just read a few fixed pixels? Without using CNN, the latency should be lower, right? Of course, the bottleneck is likely the game’s response speed.


The customers are in fixed positions, but the items they want are different. In this new version, the matchTemplate function is used for template matching. I pre-captured the items that could appear in the customer speech bubbles, so I don't have to try everything one by one when feeding them. After pressing a shortcut key, it finds all the template matches in a designated area, and then I just drag the items.

I tested the latency, and excluding the screenshot part, matching all six templates takes around 20-30 milliseconds.

The current bottleneck is the game's recognition of mouse actions. The drag operation must simulate holding the mouse down with a significant delay before dragging, and it also needs a delay before releasing. Otherwise, the items jitter and don’t follow the mouse properly (currently, the delay is close to 300 milliseconds). Is it necessary? Well, after this adjustment, my daily income increased from a little over 2000 to 2900, but I can't seem to improve it further. 

YOLO is actually unnecessary, as it’s too performance-intensive and better suited for tasks that require generalization. Traditional computer vision methods in OpenCV are much faster than YOLO, and they don’t require model training. You can solve it directly with code
Using pre-trained models in OpenCV would be more convenient and efficient

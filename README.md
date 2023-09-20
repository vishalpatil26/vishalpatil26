declare backbone map [7][7] feature map (256); //ResNet34

declare grid[49]:

declare anchor box[49] holds [shape][size]:

for i in 1 to 49.

anchor box[i] ([shape][size])= grid(shape,size):

declare obj_class;

declare location:

for i in 1 to 49:

if (degree(overlap) from anchor box[i] equals max(degree))

define obj_class;

define location:

obj_class-permute_from(anchor box.class);

location-permute_from(anchor box.loc);

permute from(anc_box_array.class(optional), loc(optional)):

for each element from anc_box_array:

get shape; //this parameter is to determine the shape of the anchor box

get size; //parameter to determine the size

get lighting: //parameter to determine the lighting

get pixel pattern; //parameter to determine the visible vs dark pixels

get aspect ratio; //parameter to determine the aspect ratio of the pixels

test cases:

if aspect ratio is like m:n where m>n then

obj has larger length

else

obj has larger height

>>if pixel pattern in ('soft edge")

obj is of complex structure and has curved edges

→ if lighting in ('dark_area") then

obj is in bedroom - inclines mostly to the bedside objects

return 'class_of_the_object

return "location_of_the_object

// object class is to determine the type of object (stationery, cutlery, smartdevices etc.)

// location gives insights on the scope of the object (bedroom objects, living room furniture

etc.)

depth_estimation:

depth obj_in_frame(obj);

if (obj_in_frame(obj) - 1) then // if the obj fits in frame detect_object(boxes, scores,

classes, num detections);

for i,b in enumerate(boxes[0]):

eval boxes[0][i][0] // y axis upper boundary coordinates eval boxes[0][1][1] // x axis left

boundary coordinates

eval boxes[0][1][2] y axis lower boundary coordinates eval boxes[0][1][3] // x axis right boundary coordinates

mid x-(boxes[0][1][1]+ boxes[0][0][3])/2;

mid y-(boxes[0][0][0] + boxes[0][1][2])2:

apx_distance round(((1 - boxes[0][i][3] - boxes[0][1][1]))**4.1); plot(mid_x,mid_y) //

plot a dot at the centre;

scores[0][i]-draw_boxes(obj);

if scores[0][i]> 0.5 then

goto next if;

else goto for..enumerate(boxes[0]);

if (apx_distance<0.5 && mid_x>0.3 && mid y <0.7): goto image_recognition();

return 'object_is_closer":

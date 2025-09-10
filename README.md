# Alzheimer-s-Disease-Data-Dashboard
Excel + SQL + Power BI Project | Retail Sales Data | From Raw Data to Business Insights
### Project Overview
I created this dashboard to make Alzheimer’s brain scan data easier  I wanted something clear and visual that shows patterns and differences across patients at a glance. This dashboard is not just about numbers. It makes the science visual and intuitive, so even someone without a technical background can follow along and see what is happening.

# Tools & Technologies
* Excel
*  SQL
*  Power BI

# Table of Contents
 [Project Overview](#Project-Overview)
* [Dataset Overview](#Dataset-Overview)
* [New measure](#New-measure)
* [Data Cleaning Process](#Data-Cleaning-Process) 
* [Key insights](#Key-insights) 
* [Power BIDashboard](#Power-BI-Dashboard)

  ### Dataset Overview
  Filename, Label	,mean_pixel_intensity	,std_pixel_intensity,entropy	,edge_density	,center_brightness	,is_augmented	,Image URL


  ### Project Overview
| Filename | Label |   mean_pixel_intensity	| std_pixel_intensity | entropy  | edge_density	|  center_brightness  |  is_augmented  |  Image URL| 
|-------|--------| --------- |-------- |----------| ---------| -------- |------- |----------|
|Mild_D_00001	| MildDemented |	54.80621|60.61424489|	2.847783502|	0.080291748	|104.5899658|	FALSE|	https://drive.google.com/uc?export=view&id=1IJi4ur_Ke1fPkLt2DlgjyGMC26YJ69Lu
|Mild_D_00002	|MildDemented|	73.52130127	|84.47605388	|3.029536133	|0.082504272	|151.3317871|	FALSE	|https://drive.google.com/uc?export=view&id=1Nw-BEVwUe4_mWXNO_dvPizqTNpq7cNI3
|Mild_D_00003|	MildDemented|	78.80847168	| 82.59391534|	3.376683209	| 0.087463379|	128.9571533	|FALSE|	https://drive.google.com/uc?export=view&id=1GADa9UzJMWN2BgNsBihpN_Oe3EHF75xK
|Mild_D_00004| 	MildDemented|	74.40574646|	77.06944174|	3.279336579|	0.080993652	|136.4750366|	FALSE	|https://drive.google.com/uc?export=view&id=161YcLWzIgVnhtJS3dSJh4GtfJ6i8xyde
|Mild_D_00005|	MildDemented|	68.12065125|	79.58237369	| 2.972923067	|0.089920044| 145.6033936	|FALSE|	https://drive.google.com/uc?export=view&id=1kDWt8fK3jujJ5ByvKf-X-TwVGoKs00cf

### Data Cleaning Process
- Converted Date to proper datetime format
- Removed missing or invalid values
- Created new calculated fields:
  Disease Progression = AVERAGE(All_Disease[Severity
Score])
Scan Disorder Level =
CALCULATE(
AVERAGE(A|_Disease [entropy]),
FILTER(All_Disease, All_Disease[Severity Score] > 0)

```NEW MEASURES
Severity Score =
SWITCH
All_Disease[Label],
"NonDemented", 0,
"VeryMildDemented", 1,
"MildDemented", 2,
"ModerateDemented", 3,
BLANK()

Disease Progression = AVERAGE(All_Disease[Severity
Score])

Scan Disorder Level =
CALCULATE(
AVERAGE(A|_Disease [entropy]),
FILTER(All_Disease, All_Disease[Severity Score] > 0)

Radiance Progression =
CALCULATE(
AVERAGE(A|_Disease (mean_pixel_intensity]),
FILTER(Al_Disease, Al_Disease [Severity Score] >= 0)

Brightness Variation =
CALCULATE(
AVERAGE(A|_Disease[sto_pixel_intensity]),
FILTER(Al_Disease, Al_Disease [Severity Score] >= 0)
``` 

### Power BI Dashboard
The Power  BI dashboard includes the following visuals:
* 📈Disease Progression 
* scan disorder progression 
* radiance progression 
*🔆 brightness variation
* Top demented scans 
* Top healthy scan
* entrophy level  
* structural clarity 
*: pixel intensity
![6ed0b058-6cf7-4250-a767-11cd7c470211](https://github.com/user-attachments/assets/0b7f1d0d-894c-412b-bca9-43bec7fcc434)
![70dfcdd8-55ab-4ded-aadf-edf3a6d33545](https://github.com/user-attachments/assets/14836bb3-91dc-4f92-8092-4b9690af8089)

### Key Insights
Key health metrics like disease progression (1.50), scan disorder level (2.92), radiance progression (74.67), brightness variation (78.91), and central brightness variation (127.53)
* Image analytics such as pixel intensity, standard deviation, and entropy for each scan
* Side-by-side comparisons of demented and healthy scans to reveal structural differences
* Entropy and clarity by diagnostic category, showing how non-demented scans hold stronger structure compared to mild or moderate cases
* Pixel intensity breakdown across groups to highlight subtle but important differences
  
### Why it’s Unique
This dashboard is not just about numbers. It makes the science visual and intuitive, so even someone without a technical background can follow along and see what is happening.

### Why I’m Proud of It
This project proves how analytics can tell a story. By mixing data with design, I built something that is detailed, clear, and actually useful for anyone who wants to understand Alzheimer’s data better.

sample file (download here)
[All_Disease.csv](https://github.com/user-attachments/files/22258134/All_Disease.csv)



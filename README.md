# Python Integration with Power BI

## Installing Python 
- Download Python.
- Install the required Python packages for Power BI by running the following commands in command prompt.
  * **Pandas**: python -m pip install pandas
  * **Matplotlib**: python -m pip install matplotlib

## Enabling Python Scripting in Power BI Desktop
- Open **Power BI Desktop**.
- Go to **File** menu.
- Under **File** menu, click on **Options and settings**. Then, click on **Options**.
- Under **Options**, click on **Python scripting**.
- Under **Python scripting**, set the required **Python home directory** and the **Python IDE**. Then, seleck **OK**.
![image](https://user-images.githubusercontent.com/49337890/147581759-ceb55425-b366-4393-9b5f-7e4c49b004d1.png)

## Running Python Scripts in Power BI Desktop
- Open **Anaconda Prompt**.
- Type "Program Files\Microsoft Power BI Desktop\bin\PBIDesktop.exe" in **Anaconda Prompt**. **Power BI Desktop** opens from **Anaconda Prompt**.
![image](https://user-images.githubusercontent.com/49337890/147568537-64775d33-35f3-4836-b1d2-eae87a1387b2.png)

### Importing Data in Power BI Desktop
- Go to **Home** menu.
- Under **Home** menu, click on **Get data**. Then, click on **More...**.
- Under **More...**, click on **Python script**.
- Run Python script to get data. Select **Connect**.
![image](https://user-images.githubusercontent.com/49337890/147578131-2f76b68b-b947-4913-8501-667dce4f991f.png)
- **Navigator** window opens. Click on the data table. Then, select **Load**.
![image](https://user-images.githubusercontent.com/49337890/147578746-9b3dc67c-5f80-460c-8f24-032807d2d5db.png)

### Visualizing Data in Power BI Desktop
- Go to **Report** tab from left panel.
- Go to **Visualizations** pane from right panel.
- Under **Visualizations** pane, click on **Py** Python visual.
- Choose the features of the data in **Fields** pane from right panel.
- **Python script editor** opens.
- Run Python script in **Python script editor** to visualize data. 
![image](https://user-images.githubusercontent.com/49337890/147581067-5cf0ad69-903d-4ab2-9423-03c6fcf170be.png)
- Plot appears in **Report**.
![image](https://user-images.githubusercontent.com/49337890/147581283-ab89d1d4-b81f-46ff-87bf-83699621f8d7.png) 

## Drawbacks of Power BI Desktop
- Unable to add another dataset from **Get data** to Power BI Desktop when already connected a dataset from Power BI datasets.


# Opening the Project
The following sample project can be opened with or without FacotoryTalk Optix Studio Pro
## With FactoryTalk Optix Studio Pro
1. Select the green **Code** dropdown
2. Copy the repository URL to the clipboard
3. Open FactoryTalk Optix Studio and sign in to obtain the FactoryTalk Optix Studio Pro Entitlement
4. Select **Open** > **Remote**, paste the repository URL in the **Remote URL** field, set the **Location**, and Select **Open**
## Without FactoryTalk Optix Studio Pro
1. Select the green **Code** dropdown
2. Select **Download ZIP**
3. Unzip the downloaded Repository to the desired location
4. Open the **.optix** file

# Introduction
The following sample project demonstrates using a ListView UI widget when directly connected to a RAEtherNetIP Tag Array.

# ListViews Screen
The ListViews Screen contains a single ListView widget. The standard ListView has been modified to add a single Node Pointer Variable called **MyUDTPointer** and is pointing at an Array called **MyUDTArray** in the **RAEtherNet_IPStation1** Station.

> [!NOTE]
> The RAEtherNet_IPStation1 ACD file can be found in the ProjectFiles/ACD directory.

The Model Property of the ListView is pointed to the MyUDTPointer pointer. This technique of adding a pointer to the Station Tag Array and then pointing the Model to the pointer forces the Array to be on scan by Optix.

![ListViewPointerConfiguration](https://github.com/cdal3/ListViewToControllerTagArray/blob/main/ProjectFiles/README%20Images/ListViewPointerConfiguration.png)

The ListViewRow that is configured for the ListView TypeSelector must have a Type definition of **Variable**. The ListViewRow must have a Variable added to it that is of the same DataType as the Array element. In this sample application, The Variable added to the ListView row is called **MyUDT** and its DataType is **MyUDT**. A dynamic link must be created between the newly created Variable and the **{RowItem}** Alias of the ListViewRow. This allows for the incoming RowItem Variable to be mapped to a matching structure for the Station Array Element.

![ListViewRowVariableConfiguration](https://github.com/cdal3/ListViewToControllerTagArray/blob/main/ProjectFiles/README%20Images/ListViewRowVariableConfiguration.png)

When referencing values within the ListViewRow use subfields of the DataType structure rather than directly referencing the {RowItem} alias.

![ListViewRowDynamicLink](https://github.com/cdal3/ListViewToControllerTagArray/blob/main/ProjectFiles/README%20Images/ListViewRowDynamicLink.png)

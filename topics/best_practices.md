# Tips

## Bookmap or map? 

Basically, if there isn't a strict requirement on the layout of a PDF output, <bookmap> or <map> doesn't make difference.  

What differs the bookmap from the map is the prefix "book-" in <bookmap>. In other words, as a larger container, <bookmap> supports richer supporting elements and attributes.

- Bookmap: container for book, webhelp, etc. Rich support in elements and attributes that wraps the topicrefs
- Map: smaller container for book, webhelp, etc.

### An example of a bookmap: 

    <?xml version="1.0" encoding="utf-8"?>
    <!DOCTYPE bookmap PUBLIC "-//OASIS//DTD DITA BookMap//EN" "bookmap.dtd">

        <bookmap>

            <title>Getting Started with the OI</title>

            <frontmatter>
                <topicref href="concepts/oi_intro.dita" format="dita"/>
            </frontmatter>
    
        <chapter>
            <topicref href="tasks/deploying_oi_in_prod.dita" format="dita">
            <topicref href="tasks/installing_oi_prod.dita" format="dita"/>
            <topicref href="tasks/configuring_handler_prober_driver.dita" format="dita"/>
            <topicref href="tasks/enabling_stdf_log.dita" format="dita"/>
            <topicref href="tasks/connecting_oi_to_server.dita" format="dita"/>
            <topicref href="tasks/connecting_oi_to_simulated_server.dita" format="dita"/>
            </topicref>
        </chapter>
  
        <chapter>
            <topicref href="references/oi_environment.dita" format="dita"/>
        </chapter>
  
        <chapter>
            <topicref href="tasks/running_test_program.dita" format="dita"/>
        </chapter>
  
        <chapter>
            <topicref href="references/test_program_structure.dita" format="dita"/>
            <topicref href="references/test_data_structure.dita" format="dita"/>
            <topicref href="references/config_files.dita" format="dita"/>
            <topicref href="references/troubleshooting.dita" format="dita"/>
        </chapter>

        </bookmap>

In this example, references to topics are wrapped by <chapter>. Above all the chapters, a frontmatter is used in as similar way as cover page in Framemaker.

### An example of map

While in <map>, this is all you have after <title>:

	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "map.dtd">
		<map>
			<title>sample</title>
		<
	</map>
Or,
			![image](https://user-images.githubusercontent.com/49274541/127173906-2d53ea59-f27c-4626-84bb-e3ea7807b6fc.png)

## Topic types

- In standard DITA, topic types include: concept, task, reference, troubleshooting
- In lightweight DITA, topic only.
- DTD, or document type definition, defines the topic type of a dita file. 
- Topic is the parent to task, concept, reference, in which task is the parent to troubleshooting type.

## Page break

In framemaker, we can set a pagebreak at the insertion point to force a page break.

In DITA, for recommended operations within a topic, see https://www.oxygenxml.com/doc/versions/23.1/ug-pdf-css/topics/dcpp_page_breaking.html 
Note that settings to force / avoid page breaks in different scenarios, settings to avoid widow and orphan paragraph, lists have been added to the css in the publishing templates.

## Automatic table layout

Automatic adjustment to table width makes big tables look nicer. In DITA, manual operations to acchieve this, for example:

	<table outputclass='auto_tbl'> ... </table>

For details, see https://www.oxygenxml.com/doc/versions/23.1/ug-pdf-css/topics/dcpp_tables.html#dcpp_tables.

I added a few settings to enable automatic table adjustment to the css file of publishing templates.

## How to use the first column as table header

In the source code of <table> in DITA, try this:

	<row>
      ...
      <entry outputclass="rotated">
            <p>Rotated</p>
      </entry>
      ...
	</row>

Corresponding settings have been made to the customization css file for publishing template.
			
## How to Customize Style with Oxygen 
1. Go to https://styles.oxygenxml.com. 
2. Configure each attribute.
3. Click **See Results** to preview the effect in PDF or Webhelp.
4. Download the style package: **Download** > **Publishing Template**.

## How to Apply the Style to Oxygen 
In Oxygen XML Editor, you need to select a transformation scenario before publishing a book in a certain format. The most frequently used format in IES DOCS is PDF. So the following instruction takes customizing PDF transformation as an example.

**Procedure**:
1. Open oXygen XML Editor v23.1.
2. Select **DITA Maps** > **Configure Transformation Scenarios**. ![image](https://user-images.githubusercontent.com/49274541/126759829-74eb1fbe-4a00-4f5b-9619-a230025de927.png)
3. Select **DITA Map PDF - based on HTML5 & CSS**. ![image](https://user-images.githubusercontent.com/49274541/126759535-afa97ada-e77a-4945-8879-c6965389f3c7.png)
4. Click **Edit**.
5. Click **Yes** to duplicate and edit the scenario. ![image](https://user-images.githubusercontent.com/49274541/126760029-6755cba7-83d8-4983-aa52-2a75f9c8b7c7.png)
6. Specify the name of this custom transformation scenario in the **Edit Scenario** window. ![image](https://user-images.githubusercontent.com/49274541/126760265-efe8ccec-ada7-4091-a41d-4efc2826b62a.png)
7. Click **Choose Custom Publishing Template**.![image](https://user-images.githubusercontent.com/49274541/126760420-2f2fc6c6-94c8-4d2d-8da4-aee5781eb20f.png)
8. Browse for a publishing template from local folder. 
9. Click **OK**.![image](https://user-images.githubusercontent.com/49274541/126760747-36142c30-b581-42ca-beed-1613a61f20f8.png)
10. Click **OK** to save the settings.

## How to Generate PDF Using a Custom Transformation Scenario
![image](https://user-images.githubusercontent.com/49274541/126761226-9f522bc0-dfba-41cc-9ce3-6caca82c06ff.png)

## Content reuse
			
### Content reuse 1: reuse the content directly
			 
![image](https://user-images.githubusercontent.com/49274541/129874995-8da15de5-d091-49e3-b286-4d1949c8ef2b.png)

![image](https://user-images.githubusercontent.com/49274541/129875048-e4091c27-acac-4795-a448-3a5f36ef31e7.png)
      
![image](https://user-images.githubusercontent.com/49274541/129875153-b3687927-9f79-4b4c-8e15-03ff31759fb8.png)



### External crossreferences to topics within the book
      
1. Press backspace at the insert point.
2. Enter *xref*.
3. Select *xref (crossreference)*.

![image](https://user-images.githubusercontent.com/49274541/129873506-a00c92c5-b8e6-4996-8294-f6ecb5902674.png)

![image](https://user-images.githubusercontent.com/49274541/129873641-e9ae8762-e626-46ab-9ec3-c0f684dc966c.png)

![image](https://user-images.githubusercontent.com/49274541/129874103-0db16515-f7c4-48d4-b6a4-d55c11786793.png)

![image](https://user-images.githubusercontent.com/49274541/129874251-ec4067e3-213c-435c-956e-fc0f026c3d69.png)

      
### Internal crossreferences
			
Let's say we want to insert an internal reference link from one section to another section within a topic:

![image](https://user-images.githubusercontent.com/49274541/129858013-c691fb49-bccb-40b6-b90a-b0a3e2ab67b9.png)

In the section 1 of this example, I want to create a reference link that links to section 2 with id=sec2.
     ![image](https://user-images.githubusercontent.com/49274541/129858936-298edace-1db4-491d-8049-494f76af130c.png)

Here's the pseudocode:
			
			<xref href="#topicID/targetElementID">XrefText</xref>

![image](https://user-images.githubusercontent.com/49274541/129871399-a3aa31bb-8371-481c-a1d8-34a049bcf27c.png)

![image](https://user-images.githubusercontent.com/49274541/129874560-bbd1c73c-087b-47d4-bd02-49f648640b3b.png)

![image](https://user-images.githubusercontent.com/49274541/129874607-8cfb5f9b-8299-422e-9491-69d70549ed69.png)

			
      
      

			I

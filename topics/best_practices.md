# Bookmap or map? 

Basically, if there isn't a strict requirement on the layout of a PDF output, <bookmap> or <map> doesn't make difference.  

What differs the bookmap from the map is the prefix "book-" in <bookmap>. In other words, as a larger container, <bookmap> supports richer supporting elements and attributes.

Here's a sample of a bookmap: 

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

While in <map>, this is all you have after <title>:

	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "map.dtd">
		<map>
			<title>sample</title>
		<
	</map>
Or,
			![image](https://user-images.githubusercontent.com/49274541/127173906-2d53ea59-f27c-4626-84bb-e3ea7807b6fc.png)


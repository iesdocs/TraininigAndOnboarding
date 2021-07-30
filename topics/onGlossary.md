# Adding a Glossary to CMS/SRM

To create a glossary entry in DITA, use the template of Glossary Entry. It is a subset of Topic. In oxygen, when you create a new topic for glossary, try:

![image](https://user-images.githubusercontent.com/49274541/127610027-32b7ccc9-0f10-4f7b-81ac-c4564d18faf1.png)

In most of the technical manuals, Glossary is designed as an independent chapter. In DITA, when you have multiple glossary entries from A to Z, use a map to 
group them in one chapter.

To distinguish glossary entries that may cover various companies, industries, or product lines, use profiles, 
which runs in a similar way as conditional text in FrameMaker.

## Topic Level: Glossary Entry

When you create a new glossary entry as a topic, initially you get the following elements/tags from the glossaryentry.dtd. Like this:

![image](https://user-images.githubusercontent.com/49274541/127611735-b9c69f96-70ae-4dc0-bc1c-9be586f94e19.png)

or in Author mode:

![image](https://user-images.githubusercontent.com/49274541/127611813-ba98a5d0-c3f8-41ca-b07e-48bc31fb7674.png)

## Topic Group Level: Glossary Group

The <glossgroup> is a specialized topic that can contain multiple <glossentry> topics within a single document. For example:
  
  <?xml version="1.0" encoding="UTF-8"?>
  
<!DOCTYPE glossgroup PUBLIC "-//OASIS//DTD DITA Glossary Group//EN" "glossgroup.dtd">
  
<glossgroup id="grossarygrp">
  
    <title>Grossary Group</title>
  
    <glossentry id="gloss1">
      
        <glossterm> AC </glossterm>
      
        <glossdef> Alternating current </glossdef>
      
    </glossentry>
  
    <glossentry id="gloss2">
      
        <glossterm> AI </glossterm>
      
        <glossdef> Artificial intelligence </glossdef>
      
    </glossentry>
  
</glossgroup>

Or in Author mode:
  
  ![image](https://user-images.githubusercontent.com/49274541/127634269-7ca05773-d7e7-45e9-b7c9-048e91ebe297.png)

 
## Map Level: Glossary Map
  
A glossary map is a map that contains glossary entry topics, or glossary list/glossary group. For example:
  
  <?xml version="1.0" encoding="UTF-8"?>
  
  <!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "map.dtd">
  
    <map id="glossary">
    
    <title>Glossary of Terms</title>
    
    <topicmeta>
      
        <shortdesc>A list of some of the computer-related terms you may run across while operating the
          
           <ph keyref="computer_model"/> computer.</shortdesc>
      
        <author>JC</author>
      
    </topicmeta>
    
    <glossref href="glossary_terms/alphanumeric.dita" keys="glossentry_alphanumeric" print="yes" toc="yes" />
    
    <glossref href="glossary_terms/ascii.dita" keys="glossentry_ascii" print="yes" toc="yes" />
    
    <glossref href="glossary_terms/baud.dita" keys="glossentry_baud" print="yes" toc="yes" />
    
    <glossref href="glossary_terms/cartridge.dita" keys="glossentry_cartridge" print="yes" toc="yes" />
    
    <glossref href="glossary_terms/cassette.dita" keys="glossentry_cassette" print="yes" toc="yes" />  
    
    <glossref href="glossary_terms/cassette_drive.dita" keys="glossentry_cassette_drive" print="yes" toc="yes" />  
    
    <glossref href="glossary_terms/cathode_ray_tube.dita" keys="glossentry_cathode_ray_tube" print="yes" toc="yes" />  
    
    <glossref href="glossary_terms/daisy_wheel_printer.dita" keys="glossentry_daisy_wheel_printer" print="yes" toc="yes" />  
    
    <glossref href="glossary_terms/digital_computer.dita" keys="glossentry_digital_computer" print="yes" toc="yes" />  
    
    <glossref href="glossary_terms/disk.dita" keys="glossentry_disk" print="yes" toc="yes" />  
    
    <glossref href="glossary_terms/diskette.dita" keys="glossentry_diskette" print="yes" toc="yes" />  
    
    <glossref href="glossary_terms/documentation.dita" keys="glossentry_documentation" print="yes" toc="yes" />  
    
    </map>
  
We can also use glossarylist:
  
    <?xml version="1.0" encoding="UTF-8"?>  
    <!DOCTYPE bookmap PUBLIC "-//OASIS//DTD DITA BookMap//EN" "bookmap.dtd">  
    <bookmap>  
    <booktitle>  
    <mainbooktitle>Main book title</mainbooktitle>  
    </booktitle>  
    <chapter href="topic.dita"/>  
    <backmatter>  
    <booklists>  
      <glossarylist href="glossary.dita" keys="gls"/>  
    </booklists>  
    </backmatter>  
    </bookmap>  

Note that in a map that contains glossarylist or glossref, keys is required. So we need to define the keys before using them in the chapter map or bookmap. Keys are defined by keydef in map file. For example:
  
    <?xml version="1.0" encoding="UTF-8"?>  
    <!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "map.dtd">  
    <map>  
    <title>Keystore Map</title>  
    <keydef keys="glossentry_disk">  
        <topicmeta>  
            <linktext>disk</linktext>  
        </topicmeta>  
    </keydef>  
    <keydef keys="glossentry_cassette_drive">  
        <topicmeta>  
            <linktext>Expansion Interface</linktext>  
        </topicmeta>  
    </keydef>  
    <keydef keys="glossentry_documentation">  
        <topicmeta>  
            <linktext>Radio Shack</linktext>  
        </topicmeta>  
      ......  
    </keydef>  
    </map>  


## Profiles for Glossary Entries

In DITA, profile is called DITAVAL. See https://www.oxygenxml.com/dita/1.3/specs/langRef/containers/ditaval-elements.html?hl=profile I'll update this section on Monday...

## References
- https://docs.oasis-open.org/dita/v1.2/os/spec/langref/glossentry.html
- https://docs.oasis-open.org/dita/v1.2/os/spec/archSpec/dita_glossary_topic.html
- https://gist.github.com/jelovirt/4a8b602a7e199b498953 
- https://www.oxygenxml.com/dita/1.3/specs/archSpec/technicalContent/dita-glossary-topic.html
- https://www.oxygenxml.com/dita/1.3/specs/archSpec/technicalContent/dita-glossarygroup-topic.html
- https://www.oxygenxml.com/dita/1.3/specs/langRef/containers/glossary-elements.html?hl=glossary
- https://www.oxygenxml.com/dita/1.3/specs/langRef/technicalContent/glossref.html?hl=glossary
- https://www.oxygenxml.com/dita/1.3/specs/langRef/technicalContent/glossgroup.html?hl=glossary

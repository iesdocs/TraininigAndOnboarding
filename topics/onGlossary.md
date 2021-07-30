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
  
  <glossgroup id="things" xml:lang="en">
    <title>Some terms</title>
      <glossentry id="bicycle">
        <glossterm>bicycle</glossterm>
        <glossdef>Human powered mode of transport
          with two wheels
        </glossdef>
        </glossentry>
      <glossentry id="fruitbat">
        <glossterm>Fruit bat</glossterm>
        <glossdef>A bat which likes fruit</glossdef>
      </glossentry>
  </glossgroup>

## Map Level: Glossary Map

## Profiles for Glossary Entries

## References
- https://docs.oasis-open.org/dita/v1.2/os/spec/langref/glossentry.html
- https://docs.oasis-open.org/dita/v1.2/os/spec/archSpec/dita_glossary_topic.html
- https://gist.github.com/jelovirt/4a8b602a7e199b498953 
- https://www.oxygenxml.com/dita/1.3/specs/archSpec/technicalContent/dita-glossary-topic.html
- https://www.oxygenxml.com/dita/1.3/specs/archSpec/technicalContent/dita-glossarygroup-topic.html
- https://www.oxygenxml.com/dita/1.3/specs/langRef/containers/glossary-elements.html?hl=glossary
- https://www.oxygenxml.com/dita/1.3/specs/langRef/technicalContent/glossref.html?hl=glossary
- https://www.oxygenxml.com/dita/1.3/specs/langRef/technicalContent/glossgroup.html?hl=glossary


### tag based organization
My notes are organized by tags.

### a list of tags 
I decided on a two level tag system. Hope the following list is self explanatory.


```
import json
from pprint import pprint
with open('tags.json') as tags_jsonfile:
    tags_data=json.load(tags_jsonfile)
#pprint(tags_data)
```


```
from IPython.core.display import HTML,display
HTML_string=""
HTML_string+="<ol>"
for subject in tags_data[u'subjects']:
    HTML_string+="<li>"+subject["id"]+"</li>"
    HTML_string+="<ol>"
    for topic in subject["topics"]:        
        HTML_string+="<li>"+topic["id"]+"</li>"
        HTML_string+="<ol>"            
        for subtopic in topic["subtopics"]:
            HTML_string+="<li>"+subtopic["id"]+"</li>"
        if HTML_string[-4:]=="<ol>":
            HTML_string=HTML_string[:-4]
        else:
            HTML_string+="</ol>"
    if HTML_string[-4:]=="<ol>":
        HTML_string=HTML_string[:-4]
    else:
        HTML_string+="</ol>"
if HTML_string[-4:]=="<ol>":
    HTML_string=HTML_string[:-4]
else:
    HTML_string+="</ol>"          
HTML(HTML_string)
```




<ol><li>Physics</li><ol><li>Classical Mechanics</li><li>Electromagnetism</li><li>Quantum Mechanics</li><li>Condensed Matter Physics</li><li>Density Functional Theory</li></ol><li>Mathematics</li><ol><li>Groups</li><li>Linear Algebra</li></ol><li>Programming</li><ol><li>Bash</li><li>Fortran</li><li>Gnuplot</li><li>Python</li><ol><li>Vanilla Python</li><li>Matplotlib</li><li>Mayavi</li></ol></ol></ol>



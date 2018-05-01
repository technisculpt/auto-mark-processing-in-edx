
# auto-mark-processing-in-edX

for a processing IDE within edXs advanced javascript problem

## edX problem template:

Note: automarking algorith is in the javascript file and returns "correct", alternatively you can return other values and implement automarking in python within the check_function(e,ans):

```
<problem>
    <customresponse cfn="check_function">
        <script type="loncapa/python">
<![CDATA[
import json
def check_function(e, ans):
    """
    "response" is a dictionary that contains two keys, "answer" and
    ""state".

    The value of "answer" is the JSON string that "getGrade" returns.
    The value of "state" is the JSON string that "getState" returns.
    Clicking either "Submit" or "Save" registers the current state.

    response = json.loads(ans)

    # You can use the value of the answer key to grade:
    answer = json.loads(response["answer"])
    return answer == "correct"

    # Or you can use the value of the state key to grade:
    """
    response = json.loads(ans)
    state = json.loads(response["state"])
    return state["selectedChoice"] == "correct"
    """
    return True
    """
]]>
        </script>
        <jsinput
            gradefn="JSInputDemo.getGrade"
            get_statefn="JSInputDemo.getState"
            set_statefn="JSInputDemo.setState"
       initial_state='{"default":"background(0);\ntext(\"hello world!\",20,50);","selectedChoice":"incorrect1"}'
            width="600"
            height="480"
            html_file="https://test.madmaker.com.au/processingIDE.html"
            title="Dropdown with Dynamic Text"
            sop="false"/>
    </customresponse>
</problem>
```
## additional info:

[Ace editor](https://ace.c9.io/)

[textarea-as-ace-editor](https://github.com/ryanburnette/textarea-as-ace-editor)

[Custom grading applications in edX 1](http://edx.readthedocs.io/projects/edx-developer-guide/en/latest/extending_platform/javascript.html)

[Custom grading applications in edX 2](http://edx.readthedocs.io/projects/edx-partner-course-staff/en/latest/exercises_tools/custom_javascript.html)

[Based of editor and processing-helper.js found here](http://processingjs.org/tools/processing-helper.html)

## preview:

![alt text](
https://challenge.madmaker.com.au/asset-v1:USYD+MM18e+2018+type@asset+block@automarkprocessing.JPG)

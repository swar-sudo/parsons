---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Multiple Parson's Problems on One Page
---
# Parsons Practice

## Parsons 1 (Line Based Grader)
Re-arrange the blocks below so they print out "Hello World!"

<div id="p1-sortableTrash" class="sortable-code"></div>
<div id="p1-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p1-feedbackLink" value="Get Feedback" type="button" />
    <input id="p1-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function() {
  var initial = "print(\"Hello\")\n" +
    "print(\" \")\n" +
    "print(\"World\")\n" +
    "print(\"!\")";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p1-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p1-sortableTrash"
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p1-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p1-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
  });
})();
</script>


## Parsons 2 (Variable Check Grader)
Construct a program that swaps the values of variables <code>x</code> and <code>y</code> using the helper variable <code>tmp</code>. You can change the names of the variables (<span class="jsparson-toggle"></span>) by clicking them.

<div id="p2-sortableTrash" class="sortable-code"></div>
<div id="p2-sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="p2-feedbackLink" value="Get Feedback" type="button" />
    <input id="p2-newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function(){
  var initial = "$$toggle::x::y::tmp$$ = $$toggle::x::y::tmp$$\n" +
    "$$toggle::x::y::tmp$$ = $$toggle::x::y::tmp$$\n" +
    "$$toggle::x::y::tmp$$ = $$toggle::x::y::tmp$$";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "p2-sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.VariableCheckGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "trashId": "p2-sortableTrash",
    "vartests": [
        {
            "message": "Testing with initial variable values x = 3 and y = 4",
            "initcode": "x = 3\ny = 4",
            "code": "",
            "variables": {}
        },
        {
            "message": "Testing with initial variable values x = 0 and y = 2",
            "initcode": "x = 0\ny = 2",
            "code": "",
            "variables": {}
        }
    ]
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#p2-newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#p2-feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
 });
})();
</script>


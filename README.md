# Range-Change-Update-Checkbox
Range Change to Update Checkbox or Checkbox Change to Update Range

### range and checkbox .js / .css
<script type="text/javascript" src="jquery-1.11.3.min.js"></script>
<script src="ion.rangeSlider.js"></script>
<link href="ion.rangeSlider.css" rel="stylesheet" />
<link href="http://materializecss.com/css/ghpages-materialize.css" rel="stylesheet" />

### range javascript
 $(function () {
    $("#Group1_RangeID, #Group2_RangeID").ionRangeSlider({
        disable: false,
        min: 0,
        max: 5,
    });
});        

### Range and checkbox html
<div style="width:500px; margin-top:50px; margin-left:25px;">
<div  id="Group1" style="width:40%; ">
    <input type="text" id="Group1_RangeID" value="" name="range" />
      <div id="Group1_RadioID">
        <p>
            <input type="checkbox" id="Group1_test1" class="wskCheckbox" name="Group1" value="1" />
            <label for="Group1_test1">Red</label>
        </p>
        <p>
            <input type="checkbox" id="Group1_test2" class="wskCheckbox"  name="Group1" value="2" />
            <label for="Group1_test2">Yellow</label>
        </p>
        <p>
            <input type="checkbox" id="Group1_test3" class="wskCheckbox" name="Group1" value="3" />
            <label for="Group1_test3">Green</label>
        </p>
        <p>
            <input type="checkbox" id="Group1_test4"  class="wskCheckbox" name="Group1" value="4" />
            <label for="Group1_test4">Black</label>
        </p>
        <p>
            <input type="checkbox" id="Group1_test5"   class="wskCheckbox"  name="Group1"  value="5" />
            <label for="Group1_test5">Brown</label>
        </p>
    </div>
</div>

//---------> range Chenge checkbox update
$("input[name=range]").on('change', function () {
    var RangeVal = $(this).val();
    var DivID = $(this).parent();
    DivID.find('.wskCheckbox').each(function () {
        if (RangeVal == $(this).val())
        {
            $(this).prop("checked", true);
        } 
        else
        {
            $(this).prop("checked", false);
        }
    });

});
//--------------< End

//---------> checkbox Chenge  Range Update
$(".wskCheckbox").on('click', function (){
    var ClickVal = $(this).val();
    var DivID = $(this).parent().parent().parent();
    var slider = DivID.find("input[name=range]").data("ionRangeSlider");    // Range components
    slider.update({
        from: ClickVal
    });
});
//--------------< End
    

# Range-Change-Update-Checkbox
Range Change to Update Checkbox or Checkbox Change to Update Range


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
    var slider = DivID.find("input[name=range]").data("ionRangeSlider");// Range components
        slider.update({
            from: ClickVal
        });
    
});
//--------------< End
    

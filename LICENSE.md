var asd;


$(document).on("pageinit", "#no1", function () {

  $("#submitData").click(function (event) {
    event.preventDefault();
    var requestData = {
      account: $(test1).val(),
      passwd: $(test2).val()
    };
    console.log(requestData);
    $.post('http://163.24.217.87/~402460026/medicalcare/mLogin.php', requestData).done(function (data) {
      var test = JSON.parse(data);
      console.log(test);
      if (test[0] == 1) {
        //asd = test[1];
        window.location.href = "#no1a";
      } else {
        $("#show").text("帳號或密碼錯誤");
      }
    });
  });
});

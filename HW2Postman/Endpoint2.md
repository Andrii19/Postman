//������ ��� 200
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
//�������� response body � json.
let response = pm.response.json();
//���������, ��� name � ������ ����� name s request (name ����� ������.)
let response_name = response.name;
console.log (response_name);
  //���������, ��� age � ������ ����� age s request (age ����� ������.)
 let response_age = response.age ;
   console.log (response.age);
   //���������, ��� salary � ������ ����� salary s request (salary ����� ������.)
   let response_salary = response.salary ;
   console.log (response.salary );
   //�������� request.
var req = request.data;
//���������, ��� name � ������ ����� name s request (name ������� �� request

pm.test("name", function () {
    pm.expect(response.name).to.eql("Andrii");
});

//���������, ��� age � ������ ����� age s request (age ������� �� request.)
pm.test("age", function () {
    pm.expect(response.age).to.eql("29");
});

//���������, ��� salary � ������ ����� salary s request (salary ������� �� request.)
pm.test("salary", function () {
    pm.expect(response.salary).to.eql(1000);
});
//������� � ������� �������� family �� response.
let fam = response.family;
console.log (fam);
//��������� ��� u_salary_1_5_year � ������ ����� salary*4 (salary ������� �� request)
var u_salary_1_5_year = pm.response.json().family.u_salary_1_5_year;
console.log("u_salary_1_5_year = ", u_salary_1_5_year);

pm.test("u_salary_1_5_year", function(){
    pm.expect(u_salary_1_5_year).to.eql(response.salary * 4);
});
console.log("u_salary_1_5_year = ", u_salary_1_5_year)
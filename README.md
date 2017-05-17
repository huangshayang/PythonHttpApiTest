1. 脚本执行入口为initTest.py，直接运行此文件就好，不用修改任何东西
2. 用例的修改，添加，删除在Case/test_case.xls文件里
3. 用例里，Data列无参数传递的情况，必须写成{}，不然会报错
4. 用例里，对于上传文件的用例，Method里改为multipart/form-data

----------------------------------------------
**建议在写用例时，按照一个功能模块对应一个接口，一个sheet，不要多个接口写在同一个模块里，接口测试不是万能的，接口测试的作用只是保证所测接口的正确，并不能代替所有测试**

----------------------------------------------
执行完测试后，可以生成html的测试报告，需要安装pytest的html测试报告(如果需要)
<pre><code>pip install pytest-html
py.test initTest.py --html=./report.html
</code></pre>
也可使用allure测试报告
<pre><code>pip install pytest_allure_adaptor</code></pre>
----------------------------------------------
更新历史：

2017-05-12：
1. 现在可以不用改动测试代码了，直接自动生成测试用例并执行，只用在excel里写好用例就好
----------------------------------------------
2017-05-02:
1. 修改了上传文件功能的实现方法
2. 用例里对于上传文件的用例，Method里改为multipart/form-data
----------------------------------------------
2017-04-28：
1. 修复在excel用例里，data里参数的值为中文时，请求的时候会出现转码的问题
2. 修复请求时的NoneType的问题
3. 修复get请求时，传递数据格式不对的问题
4. 增加测试结果里用例名的打印
5. 修改excel用例无参数传递时的格式
----------------------------------------------
2017-04-27： 
1. 增加上传文件功能.<br/>
2. excel测试用例文件模版修改，增加一列file，以及对应的脚本逻辑修改<br/>
3. 上传的测试文件excel，现放入Data文件夹下，原用例excel文件路径不变，对于要上传文件的接口，目前国内项目里不需传data，只需传file，所以上传文件的接口data不需填写，file里填写测试excel的路径即可

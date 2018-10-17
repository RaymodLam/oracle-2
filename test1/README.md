# 实验一：分析SQL执行计划，执行SQL语句的优化指导
## 查询语句1:
<pre>
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
from hr.departments d，hr.employees e
where d.department_id = e.department_id
and d.department_name in ('IT'，'Sales')
GROUP BY department_name;
</pre>
## 执行查询语句1的结果:
<pre>
DEPARTMENT_NAME                     部门总人数       平均工资
------------------------------ ---------- ----------
IT                                      5       5760
Sales                                  34 8955.88235
</pre>
## 查询语句2：
<pre>
SELECT d.department_name，count(e.job_id)as "部门总人数"，
avg(e.salary)as "平均工资"
FROM hr.departments d，hr.employees e
WHERE d.department_id = e.department_id
GROUP BY department_name
HAVING d.department_name in ('IT'，'Sales');
</pre>
## 执行查询语句2的结果:
<pre>
DEPARTMENT_NAME                     部门总人数       平均工资
------------------------------ ---------- ----------
IT                                      5       5760
Sales                                  34 8955.88235
</pre>

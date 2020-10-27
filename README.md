# apex-report-change-text-color
apex report change text color based on query

in query report :
```
SELECT
  name, 
  salary, 
  bonus,
  commission,
  CASE 
    WHEN COALESCE(bonus,0) > COALESCE(commission,0) THEN 'red'
    WHEN COALESCE(bonus,0) < COALESCE(commission,0) THEN 'green'
    WHEN COALESCE(bonus,0) = COALESCE(commission,0) THEN 'yellow'
  END as fontcolor
FROM emp;
```

And choose the ```bonus``` column and fill ```HTML Expression``` property with :

```
<span style="color:#FONTCOLOR#;">#EMPNO#</span>
```

Tested in oracle apex 19.x and 20.x

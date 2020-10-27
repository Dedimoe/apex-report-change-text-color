# apex-report-change-text-color
apex report change text color based on query

in query report :
```
SELECT
  name, 
  salary, 
  bonus,
  CASE 
    WHEN COALESCE(bonus,0) > COALESCE(commision,0) THEN 'red'
    WHEN COALESCE(bonus,0) < COALESCE(commision,0) THEN 'green'
    WHEN COALESCE(bonus,0) = COALESCE(commision,0) THEN 'yellow'
  END as fontcolor
FROM emp;
```

choose the column and fill 'HTML Expression' property with :

```
<span style="color:#FONTCOLOR#;">#EMPNO#</span>
```


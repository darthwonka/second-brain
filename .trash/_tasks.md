## Daily

```tasks
path includes Recurring Daily
not done
due today
```

## Weekly

```tasks
not done 
path includes Recurring Weekly
description regex matches /^[012][0-9]:[0-5][0-9]\s/
```

## Overdue

```tasks
path does not include Recurring Weekly
path does not include Recurring Daily
not done
due before today
```

## Due Today

```tasks
path does not include Recurring Weekly
path does not include Recurring Daily
not done
due on today
```

## In Progress

```tasks
path does not include Recurring Weekly
path does not include Recurring Daily
not done
starts before tomorrow
```

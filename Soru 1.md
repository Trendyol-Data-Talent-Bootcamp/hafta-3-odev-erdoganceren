# Soru 1) dsmbootcamp.sample.semi_structured_hw tablosundan dsmbootcamp.sample.semi_structured_hw_expected tablosunu elde etmek.

```SQL
select name, car.id as car_id, car.model as car_model,manufacture.year as manufacture_year,
array(select as struct p.id,timestamp_add(p.date,INTERVAL 3 HOUR) as date from unnest(purchase) as p) as purchase  
from `dsmbootcamp.ceren_erdogan.semi_structured_hw`
cross join unnest(car) car
cross join unnest(manufacture) manufacture on car.id = manufacture.id

```

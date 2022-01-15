## 7장 집계 연산.

### 근사치로 계산하는 distinct count 함수

```scala
import org.apache.spark.sql.functions.approx_count_distinct 

df.select(approx_count_distinct("StockCode")).show()
```

위와 같은 기능이 있음. 대용량 데이터를 다루고, 정확한 값이 중요하지 않은 경우에 가끔 사용할 것 같다.

### scala의 map기능을 이용한 groupby 연산
```scala
df.groupBy("InvoiceNo").agg("Quantity"->"avg", "Quantity"->"stddev_pop").show(2)
```
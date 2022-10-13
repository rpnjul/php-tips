# php-tips

// create array timelist
```php
function arrayTimeList()
{
  $data = [];
  $timeStart = strtotime('12:00');
  $timeEnd = strtotime('18:00');
  $duration = '+5';
  $break = "5 minutes";
  $preTime = '';
  $index = '';
  while ($timeStart <= $timeEnd) {
      if ($preTime) {
          $firstTime = $preTime;
          $secondTime = date('H:i', strtotime("-$break",$timeStart));
          $data[] = ['id'=>$firstTime,'value'=>$firstTime." WIB - ".$secondTime.' WIB'];
      }
      $preTime = date('H:i', $timeStart);
      $timeStart = strtotime($duration.' minutes', $timeStart);
  }
  return $data;
}
```

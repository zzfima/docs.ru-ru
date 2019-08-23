---
title: <serviceThrottling>
ms.date: 03/30/2017
ms.assetid: a337d064-1e64-4209-b4a9-db7fdb7e3eaf
ms.openlocfilehash: 77ed5e91f09d9e658deeb7996baaca445b4e0c90
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937111"
---
# <a name="servicethrottling"></a>\<Сервицесроттлинг >
Задает механизм настройки службы Windows Communication Foundation (WCF).  
  
 \<системой. > ServiceModel  
\<> поведения  
\<serviceBehaviors >  
\<> поведения  
\<Сервицесроттлинг >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceThrottling maxConcurrentCalls="Integer"
                   maxConcurrentInstances="Integer"
                   maxConcurrentSessions="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|maxConcurrentCalls|Положительное целое число, ограничивающее количество сообщений, обрабатываемых в текущий момент в <xref:System.ServiceModel.ServiceHost>. Вызовы, превышающие этот предел, ставятся в очередь. Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue. Значение по умолчанию: 16 * количество процессоров.|  
|maxConcurrentInstances|Положительное целое число, ограничивающее количество объектов <xref:System.ServiceModel.InstanceContext>, одновременно выполняющихся в <xref:System.ServiceModel.ServiceHost>. Запросы на создание дополнительных экземпляров ставятся в очередь и выполняются, когда происходит отступление от предельной величины. Значение по умолчанию: сумма maxConcurrentSessions и MaxConcurrentCalls|  
|maxConcurrentSessions|Положительное целое число, ограничивающее количество сеансов, которое может принять объект <xref:System.ServiceModel.ServiceHost>.<br /><br /> Служба принимает соединения сверх предела, но только каналы, количество которых меньше предельного значения, являются активными (сообщения считываются из канала). Установка этого значения на 0 эквивалентна его установке на Int32.MaxValue. Значение по умолчанию: 100 * количество процессоров.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> поведения](behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="remarks"></a>Примечания  
 Элементы регулирования ограничивают число одновременных вызовов, экземпляров или сеансов, чтобы предотвратить чрезмерное потребление ресурсов.  
  
 Каждый раз при достижении значений атрибутов происходит запись трассировки. Первая трассировка записывается как предупреждение.  
  
## <a name="example"></a>Пример  
 В следующем примере конфигурации служба допускает максимум 2 одновременно выполняющихся вызова, а максимальное количество одновременно присутствующих экземпляров равно 10. Подробный пример выполнения этого примера см. в разделе [регулирование](../../../wcf/samples/throttling.md).  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="CalculatorServiceBehavior">
      <serviceDebug includeExceptionDetailInFaults="False" />
      <serviceMetadata httpGetEnabled="True" />
      <!-- Specify throttling behavior -->
      <serviceThrottling maxConcurrentCalls="2"
                         maxConcurrentInstances="10" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
- <xref:System.ServiceModel.Configuration.ServiceThrottlingElement>
- [Использование ServiceThrottlingBehavior для управления производительностью службы WCF](../../../wcf/feature-details/using-servicethrottlingbehavior-to-control-wcf-service-performance.md)

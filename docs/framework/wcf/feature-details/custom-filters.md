---
title: "Настраиваемые фильтры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97cf247d-be0a-4057-bba9-3be5c45029d5
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d24e517a8fd63a3363d080ebbabf2c1e3306b76
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="custom-filters"></a>Настраиваемые фильтры
Пользовательские фильтры позволяют определять логику сопоставления, которую невозможно определить с помощью фильтров системных сообщений. Например, можно создать пользовательский фильтр, который хэширует определенный элемент сообщений, а затем выполняет проверку значения, чтобы определить значение, которое возвращается фильтром (true или false).  
  
## <a name="implementation"></a>Реализация  
 Пользовательский фильтр является реализацией абстрактного базового класса <xref:System.ServiceModel.Dispatcher.MessageFilter>. При реализации пользовательского фильтра конструктор может, если необходимо, принять один строковый параметр. Этот параметр содержит данные о конфигурации, которые передаются конструктору MessageFilter для предоставления значений и настроек, необходимых фильтру во время выполнения для сопоставления. Например, их можно использовать, чтобы указать значение, поиск которого в оцениваемом сообщении выполняет фильтр. В следующем примере показана базовая реализация настраиваемого фильтра сообщений, принимающего строковый параметр:  
  
```csharp  
public class MyMessageFilter: MessageFilter  
{  
    string filterData;  
    public MyMessageFilter(string filterData)  
    {  
        if(string.IsNullOrEmpty(filterData)  
            throw new ArgumentNullException("filterData");  
        this.filterData=filterData;  
    }  
    public override bool Match(System.ServiceModel.Channels.Message message)  
    {  
        ...  
        return retValue;  
    }  
    public override bool Match(System.ServiceModel.Channels.MessageBuffer buffer)  
    {  
        ...  
        return retValue;  
    }  
}  
```  
  
> [!NOTE]
>  В фактической реализации метод match содержит логику, которая будет выполняться проверка сообщения, чтобы определить, если этот фильтр сообщений должен вернуть **true** или **false**.  
  
### <a name="performance"></a>Производительность  
 Реализуя пользовательский фильтр, важно принять во внимание максимальное время, которое может потребоваться фильтру для завершения обработки сообщения. Поскольку сообщение может обрабатываться несколькими фильтрами перед тем, как будет найдено совпадение, важно убедиться, что время ожидания клиентского запроса не завершится раньше, чем сообщение смогут обработать все фильтры. Вследствие этого пользовательский фильтр должен содержать только код, необходимый для обработки содержимого или атрибутов сообщения, чтобы определить его соответствие условиям фильтра.  
  
 В целом, при реализации пользовательского фильтра следует избегать следующих действий.  
  
-   Ввод-вывод, например сохранение данных на диск или в базу данных.  
  
-   Ненужная обработка, например циклический проход по многочисленным записям в документе.  
  
-   Блокировка операций, например вызовы, которые предусматривают блокировку совместно используемых ресурсов или поиск по базе данных.  
  
 Перед использованием пользовательского фильтра в рабочей среде следует провести тесты производительности для определения средней продолжительности времени, в течение которого фильтр обрабатывает сообщение. В сумме со средним временем обработки для других фильтров, используемых в таблице фильтров, это позволит достаточно точно определить максимальное значение времени ожидания, которое необходимо задать в клиентском приложении.  
  
## <a name="usage"></a>Использование  
 Чтобы использовать пользовательский фильтр со службой маршрутизации, необходимо добавить его в таблицу фильтров, указав новую запись фильтра с типом «Пользовательский», полное имя типа фильтра сообщений и имя сборки.  Как и в случае с другими фильтрами MessageFilters, можно указать строковые данные filterData, передаваемые конструктору пользовательского фильтра.  
  
 В следующем примере показывается использование пользовательского фильтра при работе со службой маршрутизации:  
  
```xml  
<!--ROUTING SECTION -->  
<routing>  
  <filters>  
    <filter name="CustomFilter1" filterType="Custom"   
            customType="CustomAssembly.MyMessageFilter,   
            CustomAssembly" filterData="custom data" />  
  </filters>  
  <filterTables>  
    <table name="routingTable1">  
      <filters>  
        <add filterName="CustomFilter1" endpointName="CalculatorService" />  
      </filters>  
    </table>  
  </filterTables>  
</routing>  
```  
  
```csharp  
RoutingConfiguration rc = new RoutingConfiguration();  
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();  
endpointList.Add(client);  
rc.FilterTable.Add(new MyMessageFilter("CustomData"), endpointList);  
```

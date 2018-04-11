---
title: Фильтры сообщений
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- routing [WCF], message filters
ms.assetid: cb33ba49-8b1f-4099-8acb-240404a46d9a
caps.latest.revision: 8
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bd5019668e865d2fea835b450d992d45b5273ed7
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2018
---
# <a name="message-filters"></a>Фильтры сообщений
Чтобы обеспечить маршрутизацию на основе содержимого, служба маршрутизации использует реализации класса <xref:System.ServiceModel.Dispatcher.MessageFilter>, которые проверяют такие разделы сообщения, как адрес, имя конечной точки или инструкция XPath. Если ни один из фильтров, предоставляемых платформой [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)], не подходит, можно создать пользовательский фильтр, написав реализацию базового класса <xref:System.ServiceModel.Dispatcher.MessageFilter>.  
  
 При настройке службы маршрутизации, необходимо определить элементы фильтра (<xref:System.ServiceModel.Routing.Configuration.FilterElement> объектов), которые описывают тип **MessageFilter** и все дополнительные данные, необходимые для создания фильтра, например, строковые значения для поиска для сообщения. Обратите внимание, что создание элементов фильтров подразумевает только создание отдельных фильтров сообщений. Для фильтров, занимающихся вычислением и маршрутизацией сообщений, необходимо также определить таблицу фильтров (<xref:System.ServiceModel.Routing.Configuration.FilterTableEntryCollection>).  
  
 Каждая запись в таблице фильтров указывает на элемент фильтра и клиентскую конечную точку, в которую производится перенаправление сообщения при обнаружении соответствия. В записи таблицы фильтров можно также задать коллекцию резервных конечных точек (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>), содержащую список конечных точек, в которые сообщение передается в случае возникновения ошибки при отправке сообщения в основную конечную точку. Эти конечные точки перебираются в указанном порядке до тех пор, пока передача сообщения не будет выполнена успешно.  
  
## <a name="message-filters"></a>Фильтры сообщений  
 Фильтры сообщений, используемые службой маршрутизации, предоставляют основные функции выделения сообщений, например вычисление имени конечной точки, в которую отправлено сообщение, действие SOAP, а также адрес или префикс адреса, по которому отправлено сообщение. Фильтры могут быть объединены по условию `AND`, то есть сообщение будет передано в конечную точку только в случае, если выполняются оба условия. Можно создать пользовательский фильтр, создав новую реализацию класса <xref:System.ServiceModel.Dispatcher.MessageFilter>.  
  
 В следующей таблице приведены значения <xref:System.ServiceModel.Routing.Configuration.FilterType>, используемые службой маршрутизации, классы, реализующие соответствующие фильтры сообщений, а также обязательные параметры <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.  
  
|Тип фильтра|Описание|Значение данных фильтра|Пример фильтра|  
|------------------|-----------------|-------------------------|--------------------|  
|Действие|Использует класс <xref:System.ServiceModel.Dispatcher.ActionMessageFilter> для поиска сообщений, содержащих определенное действие.|Действие, по которому производится фильтрация.|\<filter name="action1" filterType="Action" filterData="http://namespace/contract/operation" />|  
|EndpointAddress|Использует <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter> класса, с <xref:System.ServiceModel.Dispatcher.EndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true` для поиска сообщений, содержащих определенный адрес.|Адрес, по которому будет выполняться фильтрация (в поле «Кому»).|\<filter name="address1" filterType="EndpointAddress" filterData="http://host/vdir/s.svc/b"  />|  
|EndpointAddressPrefix|Использует <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> класса, с <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter.IncludeHostNameInComparison%2A>  ==  `true` для поиска сообщений, содержащих определенный префикс адреса.|Адрес, по которому будет выполняться фильтрация с использованием самого длинного совпадающего префикса.|\<filter name="prefix1" filterType="EndpointAddressPrefix" filterData="http://host/" />|  
|И|Использует класс <xref:System.ServiceModel.Dispatcher.StrictAndMessageFilter>, который всегда проверяет оба условия перед возвратом результата.|параметр filterData не используется. Вместо этого filter1 и filter2 содержат имена соответствующих фильтров сообщений (также в таблице), которые должны быть **AND**объединены.|\<filter name="and1" filterType="And" filter1="address1" filter2="action1" />|  
|Другой|Определяемый пользователем тип, который расширяет класс <xref:System.ServiceModel.Dispatcher.MessageFilter> и имеет конструктор, принимающий строку.|Атрибут customType является полным именем типа для создаваемого класса. Параметр filterData - строка, передаваемая конструктору при создании фильтра.|\<filter name="custom1" filterType="Custom" customType="CustomAssembly.CustomMsgFilter, CustomAssembly" filterData="Custom Data" />|  
|EndpointName|Использует класс <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> для поиска сообщений на основе имени конечной точки службы, в которую они поступили.|Имя конечной точки службы, например: «serviceEndpoint1».  Это должна быть одна из конечных точек, представленных в службе Routing Service.|\<filter name="stock1" filterType="Endpoint" filterData="SvcEndpoint" />|  
|MatchAll|Использует класс <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>. Этот фильтр находит все поступившие сообщения.|Параметр filterData не используется. Этот фильтр всегда находит все поступившие сообщения.|\<filter name="matchAll1" filterType="MatchAll" />|  
|XPath|Использует класс <xref:System.ServiceModel.Dispatcher.XPathMessageFilter> для поиска сообщений по запросу XPath.|Запрос XPath, используемый при сопоставлении сообщений.|\<filter name="XPath1" filterType="XPath" filterData="//ns:element" />|  
  
 В следующем примере определяются записи фильтра, использующие фильтры сообщений XPath, EndpointName и PrefixEndpointAddress. В этом примере также показано применение пользовательского фильтра для записей RoundRobinFilter1 и RoundRobinFilter2.  
  
```xml  
<filters>  
     <filter name="XPathFilter" filterType="XPath"   
             filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
     <filter name="EndpointNameFilter" filterType="EndpointName"   
             filterData="calculatorEndpoint"/>  
     <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"   
             filterData="http://localhost/routingservice/router/rounding/"/>  
     <filter name="RoundRobinFilter1" filterType="Custom"   
             customType="RoutingServiceFilters.RoundRobinMessageFilter,   
             RoutingService" filterData="group1"/>  
     <filter name="RoundRobinFilter2" filterType="Custom"   
             customType="RoutingServiceFilters.RoundRobinMessageFilter,   
             RoutingService" filterData="group1"/>  
</filters>  
```  
  
> [!NOTE]
>  Простого определения фильтра недостаточно для того, чтобы он использовался для поиска сообщений. Фильтр необходимо добавить в таблицу фильтров, которая связана с конечной точкой службы, доступной службе маршрутизации.  
  
### <a name="namespace-table"></a>Таблица пространств имен  
 При использовании фильтра XPath размер данных фильтра, содержащих запрос XPath, может оказаться весьма большим из-за использования пространств имен. Чтобы избежать этого, служба маршрутизации предусматривает возможность определения собственных префиксов с помощью таблицы пространств имен.  
  
 Эта таблица представляет собой коллекцию объектов <xref:System.ServiceModel.Routing.Configuration.NamespaceElement>, в которой определены префиксы часто используемых пространств имен, которые могут быть использованы в XPath. Ниже приведены пространства имен по умолчанию и их префиксы, содержащиеся в таблице пространств имен.  
  
|Префикс|Пространство имен|  
|------------|---------------|  
|s11|http://schemas.xmlsoap.org/soap/envelope|  
|s12|http://www.w3.org/2003/05/soap-envelope|  
|wsaAugust2004|http://schemas.xmlsoap.org/ws/2004/08/addressing|  
|wsa10|http://www.w3.org/2005/08/addressing|  
|sm|http://schemas.microsoft.com/serviceModel/2004/05/xpathfunctions|  
|tempuri|http://tempuri.org|  
|ser|http://schemas.microsoft.com/2003/10/Serialization|  
  
 Если известны пространства имен, которые будут использоваться в запросах XPath, их можно добавить в таблицу пространств имен вместе с уникальными префиксами, которые затем можно использовать в запросах XPath вместо полных пространств имен. В следующем примере определяется префикс «custom» для пространства имен «http://my.custom.namespace», которое затем используется в запросе XPath, содержащемся в filterData.  
  
```xml  
<namespaceTable>  
     <add prefix="custom" namespace="http://my.custom.namespace/"/>  
</namespaceTable>  
<filters>  
     <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 1"/>  
</filters>  
```  
  
## <a name="filter-tables"></a>Таблицы фильтров  
 Поскольку каждый элемент фильтра определяет логическое сравнение, которое может быть применено к сообщению, таблица фильтров обеспечивает сопоставление между элементом фильтра и целевой клиентской конечной точкой. Таблица фильтров является именованной коллекцией объектов <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement>, определяющих сопоставление между фильтром, основной целевой конечной точкой и списком альтернативных резервных конечных точек. Записи таблицы фильтров также позволяют указывать необязательные приоритеты для каждого из условий фильтрации. В следующем примере определяются два фильтра, а затем определяется таблица фильтров, которая сопоставляет каждый из фильтров с целевой конечной точкой.  
  
```xml  
<routing>  
     <filters>  
       <filter name="AddAction" filterType="Action" filterData="Add" />  
       <filter name="SubtractAction" filterType="Action" filterData="Subtract" />  
     </filters>  
     <filterTables>  
       <table name="routingTable1">  
         <filters>  
           <add filterName="AddAction" endpointName="Addition" />  
           <add filterName="SubtractAction" endpointName="Subtraction" />  
         </filters>  
       </table>  
     </filterTables>      
</routing>  
```  
  
### <a name="filter-evaluation-priority"></a>Приоритет вычисления фильтров  
 По умолчанию все записи таблицы фильтров вычисляются одновременно. После этого производится передача сообщения в конечные точки, сопоставленные с каждой совпадающей записью фильтра. Если сразу несколько фильтров вернули значение `true`, а сообщение является односторонним или дуплексным, оно передается в конечные точки, соответствующие всем этим фильтрам. Сообщения типа «запрос-ответ» не могут быть переданы нескольким конечным точкам, поскольку клиенту должен быть возвращен всего один ответ.  
  
 Более сложную логику маршрутизации можно реализовать, задав приоритеты для каждого из фильтров. Первым делом служба маршрутизации будет отрабатывать все фильтры, имеющие наивысший уровень приоритета. Если сообщение соответствует фильтру этого уровня, то фильтры более низких уровней не вычисляются. Например, поступившее одностороннее сообщение сначала вычисляется по всем фильтрам с приоритетом 2. Ни одному из фильтров этого уровня сообщение не соответствует, поэтому далее сообщение проверяется по фильтрам уровня 1. Сообщение соответствует двум фильтрам с приоритетом 1, и, поскольку это однонаправленное сообщение, оно будет направлено в обе целевые конечные точки.  Поскольку найдено соответствие с фильтрами с приоритетом 1, вычисление фильтров уровня 0 не производится.  
  
> [!NOTE]
>  Если приоритеты не заданы, то используется уровень 0.  
  
 В следующем примере определена таблица фильтров, в которой для фильтров заданы приоритеты 2, 1 и 0.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="XPathFilter" endpointName="roundingCalcEndpoint"   
               priority="2"/>  
          <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint"   
               priority="1"/>  
          <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint"   
               priority="1"/>  
          <add filterName="MatchAllMessageFilter" endpointName="defaultCalcEndpoint"   
               priority="0"/>  
     </filterTable>  
</filterTables>  
```  
  
 В предыдущем примере, если сообщение соответствует фильтру XPathFilter, то оно будет перенаправлено в конечную точку roundingCalcEndpoint, а все остальные фильтры в таблице не будут вычисляться, поскольку имеют более низкий уровень приоритета. Однако, если сообщение не соответствует фильтру XPathFilter, будет производиться его вычисление на соответствие всем фильтрам следующего уровня - EndpointNameFilter и PrefixAddressFilter.  
  
> [!NOTE]
>  По возможности используйте монопольные фильтры вместо указания приоритетов, поскольку это может отрицательно сказаться на производительности.  
  
### <a name="backup-lists"></a>Резервные списки  
 Для каждого фильтра в таблице фильтров может быть указан резервный список, который представляет собой именованную коллекцию конечных точек (<xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection>). В этой коллекции содержится упорядоченный список конечных точек, в которые будет передано сообщение в случае возникновении события <xref:System.ServiceModel.CommunicationException> при его отправке в основную конечную точку, указанную в параметре <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.EndpointName%2A>. В следующем примере определяется резервный список с именем «backupServiceEndpoints», который содержит две конечные точки.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
 В приведенном выше примере при сбое отправки в основную конечную точку «Destination», служба маршрутизации попытается повторить отправку для каждой конечной точки в последовательности, они перечислены, отправляя последовательно и впоследствии отправку сообщения, если происходит сбой отправки последовательно. Если отправка сообщения завершилась ошибкой для всех конечных точек, возвращается ошибка.

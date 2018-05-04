---
title: '&lt;пул приложений&gt; элемент (веб-параметров)'
ms.date: 03/30/2017
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a2eafc6b5ad1446fd07518f877a8ec001ad8dbd6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltapplicationpoolgt-element-web-settings"></a>&lt;пул приложений&gt; элемент (веб-параметров)
Задает параметры конфигурации, используемого ASP.NET для управления поведением всего процесса, когда приложение ASP.NET выполняется в режиме интеграции с [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздней версии.  
  
> [!IMPORTANT]
>  Этот элемент и компонент поддерживает работает только если приложение ASP.NET размещается на [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздней версии.  
  
 \<configuration>  
\<System.Web > элемент (веб-параметров)  
\<пул приложений > элемент (веб-параметров)  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|Указывает, сколько одновременных запросов ASP.NET разрешает для каждого ЦП.|  
|`maxConcurrentThreadsPerCPU`|Указывает, сколько одновременных потоков могут одновременно выполняться для пула приложений для каждого ЦП. Это обеспечивает альтернативный способ управления параллелизмом ASP.NET, так как можно ограничить число управляемых потоков, которые могут использоваться для обслуживания запросов на один ЦП. По умолчанию этот параметр является 0, означающее, что ASP.NET не ограничивает количество потоков, которые могут быть созданы на ЦП, несмотря на то, что пул потоков CLR также ограничивает количество потоков, которые могут быть созданы.|  
|`requestQueueLimit`|Указывает максимальное число запросов, которые могут быть поставлены в очередь для ASP.NET в одном процессе. Когда два или более приложений ASP.NET выполняются в один пул приложений, этот параметр относится к общему набору запросы, выполняемые для любого приложения в пуле приложений.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Содержит сведения о том, как ASP.NET взаимодействует с ведущим приложением.|  
  
## <a name="remarks"></a>Примечания  
 При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздней версии в интегрированном режиме это сочетание элементов позволяет настроить, как ASP.NET управляет потоков и очереди запросов, если приложение размещено в пуле приложений IIS. При использовании IIS 6 или при использовании [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] в классическом режиме или режиме ISAPI эти параметры игнорируются.  
  
 `applicationPool` Параметры применяются для всех пулов приложений, работающих на определенной версии платформы .NET Framework. Параметры, содержащиеся в файле aspnet.config. Это версия этого файла для версий 2.0 и 4.0 платформы .NET Framework. (Версии 3.0 и 3.5 платформы .NET Framework, используют файл aspnet.config с версии 2.0.)  
  
> [!IMPORTANT]
>  При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] на [!INCLUDE[win7](../../../../../includes/win7-md.md)], можно настроить отдельные файлы ASPNET.config для каждого пула приложений. Это позволяет настраивать производительностью потоков для каждого пула приложений.  
  
 Для `maxConcurrentRequestsPerCPU` параметр, значение по умолчанию «5000» в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] эффективно отключает регулирование запросов, управляемое ASP.NET, если не требуется фактически 5000 или более запросов на один ЦП. Значение по умолчанию вместо зависит от пула потоков CLR автоматическое управление параллелизмом для каждого ЦП. Приложения, предусматривают широкое использование обработку асинхронного запроса или в которых много долго выполняющихся запросов, заблокированных в сетевых операций ввода-вывода, будет обеспечен предел увеличения по умолчанию в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]. Параметр `maxConcurrentRequestsPerCPU` ноль отключается использование управляемых потоков для обработки запросов ASP.NET. Если приложение выполняется в пуле приложений IIS, запросы остаются в потоке ввода-вывода в IIS, и таким образом, параллелизм регулируется параметрами потоков IIS.  
  
 `requestQueueLimit` Параметр работает так же, как `requestQueueLimit` атрибут [processModel](http://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) элемент, который задается в файлах Web.config для приложений ASP.NET. Тем не менее `requestQueueLimit` переопределяет параметр в файле aspnet.config `requestQueueLimit` в файле Web.config. Другими словами Если заданы оба атрибута (по умолчанию это значение true), `requestQueueLimit` приоритет имеет параметр в файле aspnet.config.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как настроить поведение всего процесса ASP.NET в файле aspnet.config в следующих случаях:  
  
-   Приложение размещается в [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] пула приложений.  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] работает в интегрированном режиме.  
  
-   Приложение использует [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] или более поздней версии.  
  
 В примере используются значения по умолчанию.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"  
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>Сведения об элементе  
  
|||  
|-|-|  
|Пространство имен||  
|Имя схемы||  
|Файл проверки||  
|Может быть пустым||  
  
## <a name="see-also"></a>См. также  
 [Элемент \<system.web> (веб-параметры)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)

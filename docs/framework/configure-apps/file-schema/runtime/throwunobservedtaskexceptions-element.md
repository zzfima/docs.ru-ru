---
title: "&lt;ThrowUnobservedTaskExceptions&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 635270a6461b573663b7719843d81ff2b23e63dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a>&lt;ThrowUnobservedTaskExceptions&gt; элемент
Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.  
  
 \<configuration>  
\<Среда выполнения >  
\<ThrowUnobservedTaskExceptions >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, будут ли необработанные исключения задачи завершать выполняющийся процесс.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|Не завершает выполняющийся процесс для необработанное исключение задачи. Это значение по умолчанию.|  
|`true`|Завершает выполняющийся процесс для необработанное исключение задачи.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
|||  
  
## <a name="remarks"></a>Примечания  
 Если исключение, связанное со <xref:System.Threading.Tasks.Task> не было соблюдено, имеется не <xref:System.Threading.Tasks.Task.Wait%2A> операции родительского не подключен и <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> свойство не было прочитано рассматривается как непредвиденное исключение задачи.  
  
 В [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], по умолчанию, если <xref:System.Threading.Tasks.Task> , имеет непредвиденное исключение сбора мусора, метод завершения создает исключение и завершает процесс. Завершение процесса определяется временем сбора мусора и завершения.  
  
 Чтобы упростить разработчикам в создании асинхронного кода на основе задач, [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] изменяет это поведение по умолчанию для непредвиденное исключений. Ненаблюдаемые исключения по-прежнему вызывать <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> событие, но по умолчанию не завершает процесс. Вместо этого исключение игнорируется после возникновения события независимо от того, обнаруживает ли обработчик событий, исключение.  
  
 В [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], можно использовать [ \<ThrowUnobservedTaskExceptions > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) в файле конфигурации приложения, чтобы включить [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] поведение создания исключения.  
  
 Можно также задать поведение исключения в одной из следующих способов:  
  
-   Задав переменную среды `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
-   Задав значение DWORD реестра значение ThrowUnobservedTaskExceptions = 1 в реестр\\. Ключ NETFramework.  
  
## <a name="example"></a>Пример  
 В следующем примере показано включение возникновение исключений в задачах с помощью файла конфигурации приложения.  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как непредвиденное исключение из задачи. Код должен выполняться как выпущено для правильной работы программы.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)

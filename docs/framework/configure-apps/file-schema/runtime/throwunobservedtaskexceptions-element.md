---
title: '&lt;ThrowUnobservedTaskExceptions&gt; элемент'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cd3a7a4305dc60beb73b20580049e40780f95c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515658"
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, должно ли прекратиться выполняющегося процесса необработанные исключения задачи.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание:|  
|-----------|-----------------|  
|`false`|Не прекращает выполнение запущенного процесса для необработанное исключение задачи. Это значение по умолчанию.|  
|`true`|Завершает работу выполняющегося процесса для необработанное исключение задачи.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
|||  
  
## <a name="remarks"></a>Примечания  
 Если возникает исключение, с которым связан <xref:System.Threading.Tasks.Task> не было соблюдено, существует не <xref:System.Threading.Tasks.Task.Wait%2A> операции, родительский не подключен и <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> свойство не было считано, будет считаться непредвиденное исключение задачи.  
  
 В [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], по по умолчанию, если <xref:System.Threading.Tasks.Task> , имеет непредвиденное исключение удаляется сборщиком мусора, метод завершения создает исключение и завершает процесс. Завершение процесса определяется временем мусора и финализация.  
  
 Чтобы облегчить разработчикам писать асинхронный код, основанный на задачах, [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] изменяет это поведение по умолчанию для исключений без наблюдения. Ненаблюдаемые исключения по-прежнему вызывать <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> событие, но по умолчанию не завершает процесс. Вместо этого исключение игнорируется после события, независимо от того, обнаруживает ли обработчик событий, исключение.  
  
 В [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], можно использовать [ \<ThrowUnobservedTaskExceptions > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) в файле конфигурации приложения для включения [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] поведение возникновения исключения.  
  
 Можно также указать поведение исключений в одном из следующих способов:  
  
-   Переменной среды `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
-   Установив реестра DWORD значение ThrowUnobservedTaskExceptions = 1 в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Ключ NETFramework.  
  
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
 В следующем примере показано, как непредвиденное исключение из задачи. Код должен выполняться как выпущенные программы работать правильно.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также
- [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)

---
title: "Элемент &lt;ThrowUnobservedTaskExceptions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Элемент <ThrowUnobservedTaskExceptions>"
  - "Элемент ThrowUnobservedTaskExceptions"
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Элемент &lt;ThrowUnobservedTaskExceptions&gt;
Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.  
  
## Синтаксис  
  
```vb  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Не завершает выполняющийся процесс при необработанных исключениях задачи.  Это значение по умолчанию.|  
|`true`|Завершает выполняющийся процесс при необработанных исключениях задачи.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
|||  
  
## Заметки  
 Если исключение, связанное с <xref:System.Threading.Tasks.Task> не контролировалось, нет операции <xref:System.Threading.Tasks.Task.Wait%2A>, родительский элемент не присоединен и свойство <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=fullName> не считывалось, исключение задачи считается неконтролируемым.  
  
 По умолчанию, если в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] <xref:System.Threading.Tasks.Task> с неконтролируемым исключением обрабатывается сборщиком мусора, метод завершения генерирует исключение и завершает процесс.  Завершение процесса определяется временем сборки мусора и завершения.  
  
 Чтобы упростить разработчикам написание асинхронного кода на основе задач, в [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] изменена реакция по умолчанию на неконтролируемые исключения.  Неконтролируемые исключения по\-прежнему инициируют событие <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>, но по умолчанию процесс не завершится.  Вместо этого исключение игнорируется после того, как событие происходит, вне зависимости от того, проверяет ли обработчик событий исключение.  
  
 В [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] можно использовать элемент [\<ThrowUnobservedTaskExceptions\>](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) в файле конфигурации приложения для активации поведения [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] при генерации исключений.  
  
 Можно также указать поведение при исключении одним из следующих способов:  
  
-   Установкой переменной среды `COMPlus_ThrowUnobservedTaskExceptions` \(`set COMPlus_ThrowUnobservedTaskExceptions=1`\).  
  
-   Задав значение DWORD ThrowUnobservedTaskExceptions реестра \= 1 в ключе HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\.NETFramework.  
  
## Пример  
 В следующем примере показано, как включить генерацию исключений в задачах с помощью файла конфигурации приложения.  
  
```  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
  
```  
  
## Пример  
 В следующем примере показано, как неконтролируемое исключение генерируется в задаче.  Код должен быть выполнен как окончательная версия программы для корректной работы.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
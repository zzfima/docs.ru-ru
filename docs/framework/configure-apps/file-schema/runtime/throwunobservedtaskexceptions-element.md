---
title: Элемент <ThrowUnobservedTaskExceptions>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ThrowUnobservedTaskExceptions element
- <ThrowUnobservedTaskExceptions> element
ms.assetid: cea7e588-8b8d-48d2-9ad5-8feaf3642c18
ms.openlocfilehash: de5a686bcbd88fc52173b488103f033575623d62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153819"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<ThrowUnobservedTaskExceptions> Элемент
Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.  
  
[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|attribute|Описание|  
|---------------|-----------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Уточняется, следует ли прекратить процесс выполнения необработанного выполнения.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не прекращает процесс выполнения для необработанного исключения задачи. Это значение по умолчанию.|  
|`true`|Прекращает работу процесса для необработанного исключения задачи.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
|||  
  
## <a name="remarks"></a>Remarks  
 Если исключение, связанное <xref:System.Threading.Tasks.Task> с атомом, не <xref:System.Threading.Tasks.Task.Wait%2A> было замечено, операция отсутствует, <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> родитель не прилагается, а свойство не было прочитано, исключение задачи считается ненаблюдаемым.  
  
 В системе .NET 4 по умолчанию, если <xref:System.Threading.Tasks.Task> ненаблюдаемое исключение является собранным мусором, финализатор бросает исключение и завершает процесс. Окончание процесса определяется сроками вывоза и доработки мусора.  
  
 Чтобы облегчить разработчикам написание асинхронного кода на основе задач, система .NET 4.5 изменяет это поведение по умолчанию для ненаблюдаемых исключений. Незамеченные исключения по-прежнему приводят к поднятию <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> события, но по умолчанию процесс не завершается. Вместо этого исключение игнорируется после поднятия события, независимо от того, наблюдает ли обработчик событий за исключением.  
  
 В системе .NET 4.5 можно использовать [ \<элемент ThrowUnobservedTaskExceptions> элементв](throwunobservedtaskexceptions-element.md) в файле конфигурации приложения, чтобы включить поведение .NET Framework 4, бросающее исключение.  
  
 Вы также можете указать поведение исключения одним из следующих способов:  
  
- Устанавливая переменную `COMPlus_ThrowUnobservedTaskExceptions` `set COMPlus_ThrowUnobservedTaskExceptions=1`среды ().  
  
- Установив значение dWORD реестра ThrowUnobservedTaskExceptions No 1 в\\HKEY_LOCAL_MACHINE NetFramework ключ.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как включить в брасс исключений в задачи с помощью файла конфигурации приложения.  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как ненаблюдаемое исключение выбрасывается из задачи. Код должен быть запущен как выпущенная программа для правильной работы.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [Схема параметров среды выполнения](index.md)
- [Схема конфигурации файлов](../index.md)

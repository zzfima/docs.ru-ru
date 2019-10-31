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
ms.openlocfilehash: 99eef6b8c264e21df7f4ecf9fc79dc607d484a0a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115422"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<Сровунобсерведтаскексцептионс > элемент
Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp;&nbsp;&nbsp;&nbsp; **\<сровунобсерведтаскексцептионс >**  
  
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
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, должны ли исключения необработанных задач завершать выполняющийся процесс.|  
  
## <a name="enabled-attribute"></a>Атрибут enabled  
  
|значения|Описание|  
|-----------|-----------------|  
|`false`|Не завершает выполняющийся процесс для исключения необработанной задачи. Это значение по умолчанию.|  
|`true`|Завершает выполняющийся процесс для исключения необработанной задачи.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
|||  
  
## <a name="remarks"></a>Заметки  
 Если не наблюдалось исключение, связанное с <xref:System.Threading.Tasks.Task>, то <xref:System.Threading.Tasks.Task.Wait%2A> операции нет, родительский элемент не присоединен, а свойство <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> не было считано, поэтому исключение задачи считается незамеченным.  
  
 В .NET Framework 4, по умолчанию, если <xref:System.Threading.Tasks.Task> с незамеченным исключением, выполняется сбор мусора, метод завершения создает исключение и завершает процесс. Завершение процесса определяется временем сбора мусора и финализации.  
  
 Чтобы разработчикам было проще писать асинхронный код на основе задач, .NET Framework 4,5 изменяет это поведение по умолчанию для незамеченных исключений. Незамеченные исключения по-прежнему вызывают событие <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>, но по умолчанию процесс не завершается. Вместо этого исключение пропускается после возникновения события, независимо от того, отслеживает ли обработчик событий исключение.  
  
 В .NET Framework 4,5 можно использовать [элемент\<сровунобсерведтаскексцептионс >](throwunobservedtaskexceptions-element.md) в файле конфигурации приложения, чтобы обеспечить .NET Framework 4 действия создания исключения.  
  
 Можно также указать поведение исключения одним из следующих способов.  
  
- Путем задания переменной среды `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
- Задав в реестре значение DWORD Сровунобсерведтаскексцептионс = 1 в\\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft. Ключ NETFramework.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как включить создание исключений в задачах с помощью файла конфигурации приложения.  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как выдается незамеченное исключение из задачи. Чтобы правильно работать, код должен быть запущен в качестве выпущенной программы.  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Схема параметров среды выполнения](index.md)
- [Схема файла конфигурации](../index.md)

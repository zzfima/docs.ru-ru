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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ed1e66c4aadab656455686a7a1e5028b035676a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252264"
---
# <a name="throwunobservedtaskexceptions-element"></a>\<Элемент > Сровунобсерведтаскексцептионс
Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> среды выполнения**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<Сровунобсерведтаскексцептионс >**  
  
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
  
|Значение|Описание|  
|-----------|-----------------|  
|`false`|Не завершает выполняющийся процесс для исключения необработанной задачи. Это значение по умолчанию.|  
|`true`|Завершает выполняющийся процесс для исключения необработанной задачи.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о параметрах инициализации среды выполнения.|  
|||  
  
## <a name="remarks"></a>Примечания  
 Если исключение, связанное с объектом <xref:System.Threading.Tasks.Task> , не было замечено, <xref:System.Threading.Tasks.Task.Wait%2A> то операция отсутствует, родительский элемент <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> не присоединяется, а свойство не было прочитано, поэтому исключение задачи считается незамеченным.  
  
 В .NET Framework 4, по умолчанию, если <xref:System.Threading.Tasks.Task> исключение, для которого имеется незамеченная исключительная ошибка, уничтожается сборщиком мусора, метод завершения создает исключение и завершает процесс. Завершение процесса определяется временем сбора мусора и финализации.  
  
 Чтобы разработчикам было проще писать асинхронный код на основе задач, .NET Framework 4,5 изменяет это поведение по умолчанию для незамеченных исключений. Незамеченные исключения по-прежнему <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> вызывают событие, но по умолчанию процесс не завершается. Вместо этого исключение пропускается после возникновения события, независимо от того, отслеживает ли обработчик событий исключение.  
  
 В .NET Framework 4,5 можно использовать [ \<элемент > сровунобсерведтаскексцептионс](throwunobservedtaskexceptions-element.md) в файле конфигурации приложения, чтобы обеспечить поведение .NET Framework 4 для генерации исключения.  
  
 Можно также указать поведение исключения одним из следующих способов.  
  
- Путем задания переменной `COMPlus_ThrowUnobservedTaskExceptions` среды (`set COMPlus_ThrowUnobservedTaskExceptions=1`).  
  
- Задав в реестре значение DWORD Сровунобсерведтаскексцептионс = 1 в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Ключ NETFramework.  
  
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

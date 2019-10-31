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
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="b874b-102">\<Сровунобсерведтаскексцептионс > элемент</span><span class="sxs-lookup"><span data-stu-id="b874b-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="b874b-103">Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="b874b-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
<span data-ttu-id="b874b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b874b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b874b-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="b874b-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b874b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<сровунобсерведтаскексцептионс >**</span><span class="sxs-lookup"><span data-stu-id="b874b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b874b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b874b-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b874b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b874b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b874b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b874b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b874b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b874b-110">Attributes</span></span>  
  
|<span data-ttu-id="b874b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b874b-111">Attribute</span></span>|<span data-ttu-id="b874b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b874b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b874b-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b874b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b874b-114">Указывает, должны ли исключения необработанных задач завершать выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="b874b-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b874b-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="b874b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b874b-116">значения</span><span class="sxs-lookup"><span data-stu-id="b874b-116">Value</span></span>|<span data-ttu-id="b874b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b874b-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="b874b-118">Не завершает выполняющийся процесс для исключения необработанной задачи.</span><span class="sxs-lookup"><span data-stu-id="b874b-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="b874b-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b874b-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="b874b-120">Завершает выполняющийся процесс для исключения необработанной задачи.</span><span class="sxs-lookup"><span data-stu-id="b874b-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b874b-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b874b-121">Child Elements</span></span>  
 <span data-ttu-id="b874b-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b874b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b874b-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b874b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b874b-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="b874b-124">Element</span></span>|<span data-ttu-id="b874b-125">Описание</span><span class="sxs-lookup"><span data-stu-id="b874b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b874b-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b874b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b874b-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="b874b-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="b874b-128">Заметки</span><span class="sxs-lookup"><span data-stu-id="b874b-128">Remarks</span></span>  
 <span data-ttu-id="b874b-129">Если не наблюдалось исключение, связанное с <xref:System.Threading.Tasks.Task>, то <xref:System.Threading.Tasks.Task.Wait%2A> операции нет, родительский элемент не присоединен, а свойство <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> не было считано, поэтому исключение задачи считается незамеченным.</span><span class="sxs-lookup"><span data-stu-id="b874b-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="b874b-130">В .NET Framework 4, по умолчанию, если <xref:System.Threading.Tasks.Task> с незамеченным исключением, выполняется сбор мусора, метод завершения создает исключение и завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="b874b-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="b874b-131">Завершение процесса определяется временем сбора мусора и финализации.</span><span class="sxs-lookup"><span data-stu-id="b874b-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="b874b-132">Чтобы разработчикам было проще писать асинхронный код на основе задач, .NET Framework 4,5 изменяет это поведение по умолчанию для незамеченных исключений.</span><span class="sxs-lookup"><span data-stu-id="b874b-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="b874b-133">Незамеченные исключения по-прежнему вызывают событие <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException>, но по умолчанию процесс не завершается.</span><span class="sxs-lookup"><span data-stu-id="b874b-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="b874b-134">Вместо этого исключение пропускается после возникновения события, независимо от того, отслеживает ли обработчик событий исключение.</span><span class="sxs-lookup"><span data-stu-id="b874b-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="b874b-135">В .NET Framework 4,5 можно использовать [элемент\<сровунобсерведтаскексцептионс >](throwunobservedtaskexceptions-element.md) в файле конфигурации приложения, чтобы обеспечить .NET Framework 4 действия создания исключения.</span><span class="sxs-lookup"><span data-stu-id="b874b-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="b874b-136">Можно также указать поведение исключения одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="b874b-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="b874b-137">Путем задания переменной среды `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="b874b-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="b874b-138">Задав в реестре значение DWORD Сровунобсерведтаскексцептионс = 1 в\\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft. Ключ NETFramework.</span><span class="sxs-lookup"><span data-stu-id="b874b-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b874b-139">Пример</span><span class="sxs-lookup"><span data-stu-id="b874b-139">Example</span></span>  
 <span data-ttu-id="b874b-140">В следующем примере показано, как включить создание исключений в задачах с помощью файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="b874b-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="b874b-141">Пример</span><span class="sxs-lookup"><span data-stu-id="b874b-141">Example</span></span>  
 <span data-ttu-id="b874b-142">В следующем примере показано, как выдается незамеченное исключение из задачи.</span><span class="sxs-lookup"><span data-stu-id="b874b-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="b874b-143">Чтобы правильно работать, код должен быть запущен в качестве выпущенной программы.</span><span class="sxs-lookup"><span data-stu-id="b874b-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b874b-144">См. также</span><span class="sxs-lookup"><span data-stu-id="b874b-144">See also</span></span>

- [<span data-ttu-id="b874b-145">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="b874b-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b874b-146">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="b874b-146">Configuration File Schema</span></span>](../index.md)

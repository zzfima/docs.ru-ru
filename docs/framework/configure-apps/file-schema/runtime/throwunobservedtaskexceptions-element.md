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
ms.openlocfilehash: 876452a0a56d10f169526138cdbbbd153572f457
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658846"
---
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="efc0f-102">\<Элемент > Сровунобсерведтаскексцептионс</span><span class="sxs-lookup"><span data-stu-id="efc0f-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="efc0f-103">Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="efc0f-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="efc0f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="efc0f-104">\<configuration></span></span>  
<span data-ttu-id="efc0f-105">\<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="efc0f-105">\<runtime></span></span>  
<span data-ttu-id="efc0f-106">\<Сровунобсерведтаскексцептионс ></span><span class="sxs-lookup"><span data-stu-id="efc0f-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc0f-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efc0f-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efc0f-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="efc0f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="efc0f-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="efc0f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efc0f-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="efc0f-110">Attributes</span></span>  
  
|<span data-ttu-id="efc0f-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="efc0f-111">Attribute</span></span>|<span data-ttu-id="efc0f-112">Описание</span><span class="sxs-lookup"><span data-stu-id="efc0f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="efc0f-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="efc0f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="efc0f-114">Указывает, должны ли исключения необработанных задач завершать выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="efc0f-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="efc0f-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="efc0f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="efc0f-116">Значение</span><span class="sxs-lookup"><span data-stu-id="efc0f-116">Value</span></span>|<span data-ttu-id="efc0f-117">Описание</span><span class="sxs-lookup"><span data-stu-id="efc0f-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="efc0f-118">Не завершает выполняющийся процесс для исключения необработанной задачи.</span><span class="sxs-lookup"><span data-stu-id="efc0f-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="efc0f-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="efc0f-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="efc0f-120">Завершает выполняющийся процесс для исключения необработанной задачи.</span><span class="sxs-lookup"><span data-stu-id="efc0f-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efc0f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="efc0f-121">Child Elements</span></span>  
 <span data-ttu-id="efc0f-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="efc0f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="efc0f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="efc0f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="efc0f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="efc0f-124">Element</span></span>|<span data-ttu-id="efc0f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="efc0f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="efc0f-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="efc0f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="efc0f-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="efc0f-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="efc0f-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="efc0f-128">Remarks</span></span>  
 <span data-ttu-id="efc0f-129">Если исключение, связанное с объектом <xref:System.Threading.Tasks.Task> , не было замечено, <xref:System.Threading.Tasks.Task.Wait%2A> то операция отсутствует, родительский элемент <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> не присоединяется, а свойство не было прочитано, поэтому исключение задачи считается незамеченным.</span><span class="sxs-lookup"><span data-stu-id="efc0f-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="efc0f-130">В .NET Framework 4, по умолчанию, если <xref:System.Threading.Tasks.Task> исключение, для которого имеется незамеченная исключительная ошибка, уничтожается сборщиком мусора, метод завершения создает исключение и завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="efc0f-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="efc0f-131">Завершение процесса определяется временем сбора мусора и финализации.</span><span class="sxs-lookup"><span data-stu-id="efc0f-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="efc0f-132">Чтобы разработчикам было проще писать асинхронный код на основе задач, .NET Framework 4,5 изменяет это поведение по умолчанию для незамеченных исключений.</span><span class="sxs-lookup"><span data-stu-id="efc0f-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="efc0f-133">Незамеченные исключения по-прежнему <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> вызывают событие, но по умолчанию процесс не завершается.</span><span class="sxs-lookup"><span data-stu-id="efc0f-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="efc0f-134">Вместо этого исключение пропускается после возникновения события, независимо от того, отслеживает ли обработчик событий исключение.</span><span class="sxs-lookup"><span data-stu-id="efc0f-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="efc0f-135">В .NET Framework 4,5 можно использовать [ \<элемент > сровунобсерведтаскексцептионс](throwunobservedtaskexceptions-element.md) в файле конфигурации приложения, чтобы обеспечить поведение .NET Framework 4 для генерации исключения.</span><span class="sxs-lookup"><span data-stu-id="efc0f-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="efc0f-136">Можно также указать поведение исключения одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="efc0f-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="efc0f-137">Путем задания переменной `COMPlus_ThrowUnobservedTaskExceptions` среды (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="efc0f-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="efc0f-138">Задав в реестре значение DWORD Сровунобсерведтаскексцептионс = 1 в HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Ключ NETFramework.</span><span class="sxs-lookup"><span data-stu-id="efc0f-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="efc0f-139">Пример</span><span class="sxs-lookup"><span data-stu-id="efc0f-139">Example</span></span>  
 <span data-ttu-id="efc0f-140">В следующем примере показано, как включить создание исключений в задачах с помощью файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="efc0f-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="efc0f-141">Пример</span><span class="sxs-lookup"><span data-stu-id="efc0f-141">Example</span></span>  
 <span data-ttu-id="efc0f-142">В следующем примере показано, как выдается незамеченное исключение из задачи.</span><span class="sxs-lookup"><span data-stu-id="efc0f-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="efc0f-143">Чтобы правильно работать, код должен быть запущен в качестве выпущенной программы.</span><span class="sxs-lookup"><span data-stu-id="efc0f-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="efc0f-144">См. также</span><span class="sxs-lookup"><span data-stu-id="efc0f-144">See also</span></span>

- [<span data-ttu-id="efc0f-145">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="efc0f-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="efc0f-146">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="efc0f-146">Configuration File Schema</span></span>](../index.md)

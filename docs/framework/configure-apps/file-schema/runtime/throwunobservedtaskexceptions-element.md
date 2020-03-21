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
# <a name="throwunobservedtaskexceptions-element"></a><span data-ttu-id="817a9-102">\<ThrowUnobservedTaskExceptions> Элемент</span><span class="sxs-lookup"><span data-stu-id="817a9-102">\<ThrowUnobservedTaskExceptions> Element</span></span>
<span data-ttu-id="817a9-103">Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="817a9-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
<span data-ttu-id="817a9-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="817a9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="817a9-105">&nbsp;&nbsp;[**\<>выполнения**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="817a9-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="817a9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**</span><span class="sxs-lookup"><span data-stu-id="817a9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<ThrowUnobservedTaskExceptions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="817a9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="817a9-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="817a9-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="817a9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="817a9-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="817a9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="817a9-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="817a9-110">Attributes</span></span>  
  
|<span data-ttu-id="817a9-111">attribute</span><span class="sxs-lookup"><span data-stu-id="817a9-111">Attribute</span></span>|<span data-ttu-id="817a9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="817a9-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="817a9-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="817a9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="817a9-114">Уточняется, следует ли прекратить процесс выполнения необработанного выполнения.</span><span class="sxs-lookup"><span data-stu-id="817a9-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="817a9-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="817a9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="817a9-116">Значение</span><span class="sxs-lookup"><span data-stu-id="817a9-116">Value</span></span>|<span data-ttu-id="817a9-117">Описание</span><span class="sxs-lookup"><span data-stu-id="817a9-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="817a9-118">Не прекращает процесс выполнения для необработанного исключения задачи.</span><span class="sxs-lookup"><span data-stu-id="817a9-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="817a9-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="817a9-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="817a9-120">Прекращает работу процесса для необработанного исключения задачи.</span><span class="sxs-lookup"><span data-stu-id="817a9-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="817a9-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="817a9-121">Child Elements</span></span>  
 <span data-ttu-id="817a9-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="817a9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="817a9-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="817a9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="817a9-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="817a9-124">Element</span></span>|<span data-ttu-id="817a9-125">Описание</span><span class="sxs-lookup"><span data-stu-id="817a9-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="817a9-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="817a9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="817a9-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="817a9-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="817a9-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="817a9-128">Remarks</span></span>  
 <span data-ttu-id="817a9-129">Если исключение, связанное <xref:System.Threading.Tasks.Task> с атомом, не <xref:System.Threading.Tasks.Task.Wait%2A> было замечено, операция отсутствует, <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> родитель не прилагается, а свойство не было прочитано, исключение задачи считается ненаблюдаемым.</span><span class="sxs-lookup"><span data-stu-id="817a9-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="817a9-130">В системе .NET 4 по умолчанию, если <xref:System.Threading.Tasks.Task> ненаблюдаемое исключение является собранным мусором, финализатор бросает исключение и завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="817a9-130">In the .NET Framework 4, by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="817a9-131">Окончание процесса определяется сроками вывоза и доработки мусора.</span><span class="sxs-lookup"><span data-stu-id="817a9-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="817a9-132">Чтобы облегчить разработчикам написание асинхронного кода на основе задач, система .NET 4.5 изменяет это поведение по умолчанию для ненаблюдаемых исключений.</span><span class="sxs-lookup"><span data-stu-id="817a9-132">To make it easier for developers to write asynchronous code based on tasks, the .NET Framework 4.5 changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="817a9-133">Незамеченные исключения по-прежнему приводят к поднятию <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> события, но по умолчанию процесс не завершается.</span><span class="sxs-lookup"><span data-stu-id="817a9-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="817a9-134">Вместо этого исключение игнорируется после поднятия события, независимо от того, наблюдает ли обработчик событий за исключением.</span><span class="sxs-lookup"><span data-stu-id="817a9-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="817a9-135">В системе .NET 4.5 можно использовать [ \<элемент ThrowUnobservedTaskExceptions> элементв](throwunobservedtaskexceptions-element.md) в файле конфигурации приложения, чтобы включить поведение .NET Framework 4, бросающее исключение.</span><span class="sxs-lookup"><span data-stu-id="817a9-135">In the .NET Framework 4.5, you can use the [\<ThrowUnobservedTaskExceptions> element](throwunobservedtaskexceptions-element.md) in an application configuration file to enable the .NET Framework 4 behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="817a9-136">Вы также можете указать поведение исключения одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="817a9-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
- <span data-ttu-id="817a9-137">Устанавливая переменную `COMPlus_ThrowUnobservedTaskExceptions` `set COMPlus_ThrowUnobservedTaskExceptions=1`среды ().</span><span class="sxs-lookup"><span data-stu-id="817a9-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
- <span data-ttu-id="817a9-138">Установив значение dWORD реестра ThrowUnobservedTaskExceptions No 1 в\\HKEY_LOCAL_MACHINE NetFramework ключ.</span><span class="sxs-lookup"><span data-stu-id="817a9-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="817a9-139">Пример</span><span class="sxs-lookup"><span data-stu-id="817a9-139">Example</span></span>  
 <span data-ttu-id="817a9-140">В следующем примере показано, как включить в брасс исключений в задачи с помощью файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="817a9-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>
    <runtime>
        <ThrowUnobservedTaskExceptions enabled="true"/>
    </runtime>
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="817a9-141">Пример</span><span class="sxs-lookup"><span data-stu-id="817a9-141">Example</span></span>  
 <span data-ttu-id="817a9-142">Следующий пример показывает, как ненаблюдаемое исключение выбрасывается из задачи.</span><span class="sxs-lookup"><span data-stu-id="817a9-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="817a9-143">Код должен быть запущен как выпущенная программа для правильной работы.</span><span class="sxs-lookup"><span data-stu-id="817a9-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="817a9-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="817a9-144">See also</span></span>

- [<span data-ttu-id="817a9-145">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="817a9-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="817a9-146">Схема конфигурации файлов</span><span class="sxs-lookup"><span data-stu-id="817a9-146">Configuration File Schema</span></span>](../index.md)

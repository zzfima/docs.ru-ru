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
ms.openlocfilehash: 3f72bedbaaf0b15ade7ff6b7b8c3edcdfd3fda6d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749430"
---
# <a name="ltthrowunobservedtaskexceptionsgt-element"></a><span data-ttu-id="5dc44-102">&lt;ThrowUnobservedTaskExceptions&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="5dc44-102">&lt;ThrowUnobservedTaskExceptions&gt; Element</span></span>
<span data-ttu-id="5dc44-103">Определяет, будут ли необработанные исключения задачи завершать выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="5dc44-103">Specifies whether unhandled task exceptions should terminate a running process.</span></span>  
  
 <span data-ttu-id="5dc44-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5dc44-104">\<configuration></span></span>  
<span data-ttu-id="5dc44-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="5dc44-105">\<runtime></span></span>  
<span data-ttu-id="5dc44-106">\<ThrowUnobservedTaskExceptions ></span><span class="sxs-lookup"><span data-stu-id="5dc44-106">\<ThrowUnobservedTaskExceptions></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dc44-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5dc44-107">Syntax</span></span>  
  
```xml  
<ThrowUnobservedTaskExceptions  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dc44-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5dc44-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5dc44-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5dc44-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dc44-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5dc44-110">Attributes</span></span>  
  
|<span data-ttu-id="5dc44-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5dc44-111">Attribute</span></span>|<span data-ttu-id="5dc44-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5dc44-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="5dc44-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="5dc44-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="5dc44-114">Указывает, будут ли необработанные исключения задачи завершать выполняющийся процесс.</span><span class="sxs-lookup"><span data-stu-id="5dc44-114">Specifies whether unhandled task exceptions should terminate the running process.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="5dc44-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="5dc44-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="5dc44-116">Значение</span><span class="sxs-lookup"><span data-stu-id="5dc44-116">Value</span></span>|<span data-ttu-id="5dc44-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5dc44-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="5dc44-118">Не завершает выполняющийся процесс для необработанное исключение задачи.</span><span class="sxs-lookup"><span data-stu-id="5dc44-118">Does not terminate the running process for an unhandled task exception.</span></span> <span data-ttu-id="5dc44-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5dc44-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="5dc44-120">Завершает выполняющийся процесс для необработанное исключение задачи.</span><span class="sxs-lookup"><span data-stu-id="5dc44-120">Terminates the running process for an unhandled task exception.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5dc44-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5dc44-121">Child Elements</span></span>  
 <span data-ttu-id="5dc44-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5dc44-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5dc44-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5dc44-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5dc44-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="5dc44-124">Element</span></span>|<span data-ttu-id="5dc44-125">Описание</span><span class="sxs-lookup"><span data-stu-id="5dc44-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5dc44-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5dc44-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5dc44-127">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="5dc44-127">Contains information about runtime initialization options.</span></span>|  
|||  
  
## <a name="remarks"></a><span data-ttu-id="5dc44-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="5dc44-128">Remarks</span></span>  
 <span data-ttu-id="5dc44-129">Если исключение, связанное со <xref:System.Threading.Tasks.Task> не было соблюдено, имеется не <xref:System.Threading.Tasks.Task.Wait%2A> операции родительского не подключен и <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> свойство не было прочитано рассматривается как непредвиденное исключение задачи.</span><span class="sxs-lookup"><span data-stu-id="5dc44-129">If an exception that is associated with a <xref:System.Threading.Tasks.Task> has not been observed, there is no <xref:System.Threading.Tasks.Task.Wait%2A> operation, the parent is not attached, and the <xref:System.Threading.Tasks.Task.Exception%2A?displayProperty=nameWithType> property was not read the task exception is considered to be unobserved.</span></span>  
  
 <span data-ttu-id="5dc44-130">В [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], по умолчанию, если <xref:System.Threading.Tasks.Task> , имеет непредвиденное исключение сбора мусора, метод завершения создает исключение и завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="5dc44-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], by default, if a <xref:System.Threading.Tasks.Task> that has an unobserved exception is garbage collected, the finalizer throws an exception and terminates the process.</span></span> <span data-ttu-id="5dc44-131">Завершение процесса определяется временем сбора мусора и завершения.</span><span class="sxs-lookup"><span data-stu-id="5dc44-131">The termination of the process is determined by the timing of garbage collection and finalization.</span></span>  
  
 <span data-ttu-id="5dc44-132">Чтобы упростить разработчикам в создании асинхронного кода на основе задач, [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] изменяет это поведение по умолчанию для непредвиденное исключений.</span><span class="sxs-lookup"><span data-stu-id="5dc44-132">To make it easier for developers to write asynchronous code based on tasks, the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] changes this default behavior for unobserved exceptions.</span></span> <span data-ttu-id="5dc44-133">Ненаблюдаемые исключения по-прежнему вызывать <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> событие, но по умолчанию не завершает процесс.</span><span class="sxs-lookup"><span data-stu-id="5dc44-133">Unobserved exceptions still cause the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException> event to be raised, but by default, the process does not terminate.</span></span> <span data-ttu-id="5dc44-134">Вместо этого исключение игнорируется после возникновения события независимо от того, обнаруживает ли обработчик событий, исключение.</span><span class="sxs-lookup"><span data-stu-id="5dc44-134">Instead, the exception is ignored after the event is raised, regardless of whether an event handler observes the exception.</span></span>  
  
 <span data-ttu-id="5dc44-135">В [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], можно использовать [ \<ThrowUnobservedTaskExceptions > элемент](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) в файле конфигурации приложения, чтобы включить [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] поведение создания исключения.</span><span class="sxs-lookup"><span data-stu-id="5dc44-135">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], you can use the [\<ThrowUnobservedTaskExceptions> element](../../../../../docs/framework/configure-apps/file-schema/runtime/throwunobservedtaskexceptions-element.md) in an application configuration file to enable the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] behavior of throwing an exception.</span></span>  
  
 <span data-ttu-id="5dc44-136">Можно также задать поведение исключения в одной из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="5dc44-136">You can also specify the exception behavior in one of the following ways:</span></span>  
  
-   <span data-ttu-id="5dc44-137">Задав переменную среды `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span><span class="sxs-lookup"><span data-stu-id="5dc44-137">By setting the environment variable `COMPlus_ThrowUnobservedTaskExceptions` (`set COMPlus_ThrowUnobservedTaskExceptions=1`).</span></span>  
  
-   <span data-ttu-id="5dc44-138">Задав значение DWORD реестра значение ThrowUnobservedTaskExceptions = 1 в реестр\\. Ключ NETFramework.</span><span class="sxs-lookup"><span data-stu-id="5dc44-138">By setting the registry DWORD value ThrowUnobservedTaskExceptions = 1 in the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5dc44-139">Пример</span><span class="sxs-lookup"><span data-stu-id="5dc44-139">Example</span></span>  
 <span data-ttu-id="5dc44-140">В следующем примере показано включение возникновение исключений в задачах с помощью файла конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="5dc44-140">The following example shows how to enable the throwing of exceptions in tasks by using an application configuration file.</span></span>  
  
```xml  
<configuration>   
    <runtime>   
        <ThrowUnobservedTaskExceptions enabled="true"/>   
    </runtime>   
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="5dc44-141">Пример</span><span class="sxs-lookup"><span data-stu-id="5dc44-141">Example</span></span>  
 <span data-ttu-id="5dc44-142">В следующем примере показано, как непредвиденное исключение из задачи.</span><span class="sxs-lookup"><span data-stu-id="5dc44-142">The following example demonstrates how an unobserved exception is thrown from a task.</span></span> <span data-ttu-id="5dc44-143">Код должен выполняться как выпущено для правильной работы программы.</span><span class="sxs-lookup"><span data-stu-id="5dc44-143">The code must be run as a released program to work correctly.</span></span>  
  
 [!code-csharp[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/throwunobservedtaskexceptions/cs/program.cs#1)]
 [!code-vb[ThrowUnobservedTaskExceptions#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/throwunobservedtaskexceptions/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5dc44-144">См. также</span><span class="sxs-lookup"><span data-stu-id="5dc44-144">See Also</span></span>  
 [<span data-ttu-id="5dc44-145">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="5dc44-145">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="5dc44-146">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="5dc44-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

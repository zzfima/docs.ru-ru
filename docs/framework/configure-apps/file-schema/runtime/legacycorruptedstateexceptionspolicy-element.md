---
title: Элемент <legacyCorruptedStateExceptionsPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a787315ff8b016beff8fb8457619a462e5f3180
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264644"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="bb5df-102">\<legacyCorruptedStateExceptionsPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="bb5df-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="bb5df-103">Указывает, допускает ли среда CLR управляемому коду перехватывать нарушения прав доступа и другие исключения поврежденного состояния.</span><span class="sxs-lookup"><span data-stu-id="bb5df-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="bb5df-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bb5df-104">\<configuration></span></span>  
<span data-ttu-id="bb5df-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="bb5df-105">\<runtime></span></span>  
<span data-ttu-id="bb5df-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="bb5df-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb5df-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb5df-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb5df-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bb5df-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bb5df-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bb5df-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb5df-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bb5df-110">Attributes</span></span>  
  
|<span data-ttu-id="bb5df-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bb5df-111">Attribute</span></span>|<span data-ttu-id="bb5df-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bb5df-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="bb5df-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="bb5df-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="bb5df-114">Указывает, что приложение будет перехватывать сбои поврежденного состояния исключение как нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="bb5df-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bb5df-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="bb5df-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="bb5df-116">Значение</span><span class="sxs-lookup"><span data-stu-id="bb5df-116">Value</span></span>|<span data-ttu-id="bb5df-117">Описание</span><span class="sxs-lookup"><span data-stu-id="bb5df-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="bb5df-118">Приложение не будет перехватывать сбои поврежденного состояния исключение как нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="bb5df-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="bb5df-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bb5df-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="bb5df-120">Приложение будет перехватывать сбои поврежденного состояния исключение как нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="bb5df-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb5df-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bb5df-121">Child Elements</span></span>  
 <span data-ttu-id="bb5df-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bb5df-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb5df-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bb5df-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bb5df-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="bb5df-124">Element</span></span>|<span data-ttu-id="bb5df-125">Описание</span><span class="sxs-lookup"><span data-stu-id="bb5df-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bb5df-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb5df-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bb5df-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="bb5df-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb5df-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="bb5df-128">Remarks</span></span>  
 <span data-ttu-id="bb5df-129">В .NET Framework версии 3.5 и более ранних версий среда CLR может управляемого кода для перехвата исключений, которые были вызваны поврежденных состояний процесса.</span><span class="sxs-lookup"><span data-stu-id="bb5df-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="bb5df-130">Нарушение прав доступа является примером исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="bb5df-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="bb5df-131">Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], управляемый код больше не перехватывает исключения в этих типов `catch` блоков.</span><span class="sxs-lookup"><span data-stu-id="bb5df-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="bb5df-132">Тем не менее можно переопределить это изменение и продолжить обработку исключений поврежденного состояния двумя способами:</span><span class="sxs-lookup"><span data-stu-id="bb5df-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
-   <span data-ttu-id="bb5df-133">Задайте `<legacyCorruptedStateExceptionsPolicy>` элемента `enabled` атрибут `true`.</span><span class="sxs-lookup"><span data-stu-id="bb5df-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="bb5df-134">Этот параметр конфигурации применяется целиком к процессу и влияет на все методы.</span><span class="sxs-lookup"><span data-stu-id="bb5df-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="bb5df-135">- или -</span><span class="sxs-lookup"><span data-stu-id="bb5df-135">-or-</span></span>  
  
-   <span data-ttu-id="bb5df-136">Применить <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> атрибут к методу, который содержит исключения `catch` блока.</span><span class="sxs-lookup"><span data-stu-id="bb5df-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="bb5df-137">Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="bb5df-137">This configuration element is available only in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb5df-138">Пример</span><span class="sxs-lookup"><span data-stu-id="bb5df-138">Example</span></span>  
 <span data-ttu-id="bb5df-139">Приведенный ниже показано, как указать, что приложение следует вернуться к поведению перед [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]и перехватить все сбои поврежденного состояния исключения.</span><span class="sxs-lookup"><span data-stu-id="bb5df-139">The following example shows how to specify that the application should revert to the behavior before the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb5df-140">См. также</span><span class="sxs-lookup"><span data-stu-id="bb5df-140">See also</span></span>
- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="bb5df-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="bb5df-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="bb5df-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="bb5df-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

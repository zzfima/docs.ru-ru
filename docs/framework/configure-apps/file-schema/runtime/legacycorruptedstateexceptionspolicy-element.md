---
title: Элемент <legacyCorruptedStateExceptionsPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8733e11aba30ebea30fc71a5350f76dfd041eb4
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456412"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="51ddb-102">\<legacyCorruptedStateExceptionsPolicy > элемент</span><span class="sxs-lookup"><span data-stu-id="51ddb-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="51ddb-103">Указывает, допускает ли среда CLR управляемому коду перехватывать нарушения прав доступа и другие исключения поврежденного состояния.</span><span class="sxs-lookup"><span data-stu-id="51ddb-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="51ddb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="51ddb-104">\<configuration></span></span>  
<span data-ttu-id="51ddb-105">\<Среда выполнения ></span><span class="sxs-lookup"><span data-stu-id="51ddb-105">\<runtime></span></span>  
<span data-ttu-id="51ddb-106">\<legacyCorruptedStateExceptionsPolicy></span><span class="sxs-lookup"><span data-stu-id="51ddb-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ddb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="51ddb-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51ddb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="51ddb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="51ddb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="51ddb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51ddb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="51ddb-110">Attributes</span></span>  
  
|<span data-ttu-id="51ddb-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="51ddb-111">Attribute</span></span>|<span data-ttu-id="51ddb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="51ddb-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="51ddb-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="51ddb-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="51ddb-114">Указывает, что приложение будет перехватывать сбои поврежденного состояния исключение как нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="51ddb-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="51ddb-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="51ddb-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="51ddb-116">Значение</span><span class="sxs-lookup"><span data-stu-id="51ddb-116">Value</span></span>|<span data-ttu-id="51ddb-117">Описание</span><span class="sxs-lookup"><span data-stu-id="51ddb-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="51ddb-118">Приложение не будет перехватывать сбои поврежденного состояния исключение как нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="51ddb-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="51ddb-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="51ddb-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="51ddb-120">Приложение будет перехватывать сбои поврежденного состояния исключение как нарушение прав доступа.</span><span class="sxs-lookup"><span data-stu-id="51ddb-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51ddb-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="51ddb-121">Child Elements</span></span>  
 <span data-ttu-id="51ddb-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="51ddb-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51ddb-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="51ddb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="51ddb-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="51ddb-124">Element</span></span>|<span data-ttu-id="51ddb-125">Описание</span><span class="sxs-lookup"><span data-stu-id="51ddb-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="51ddb-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="51ddb-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="51ddb-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="51ddb-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51ddb-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="51ddb-128">Remarks</span></span>  
 <span data-ttu-id="51ddb-129">В .NET Framework версии 3.5 и более ранних версий среда CLR может управляемого кода для перехвата исключений, которые были вызваны поврежденных состояний процесса.</span><span class="sxs-lookup"><span data-stu-id="51ddb-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="51ddb-130">Нарушение прав доступа является примером исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="51ddb-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="51ddb-131">Начиная с [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], управляемый код больше не перехватывает исключения в этих типов `catch` блоков.</span><span class="sxs-lookup"><span data-stu-id="51ddb-131">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="51ddb-132">Тем не менее можно переопределить это изменение и продолжить обработку исключений поврежденного состояния двумя способами:</span><span class="sxs-lookup"><span data-stu-id="51ddb-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="51ddb-133">Задайте `<legacyCorruptedStateExceptionsPolicy>` элемента `enabled` атрибут `true`.</span><span class="sxs-lookup"><span data-stu-id="51ddb-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="51ddb-134">Этот параметр конфигурации применяется целиком к процессу и влияет на все методы.</span><span class="sxs-lookup"><span data-stu-id="51ddb-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="51ddb-135">-или-</span><span class="sxs-lookup"><span data-stu-id="51ddb-135">-or-</span></span>  
  
- <span data-ttu-id="51ddb-136">Применить <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> атрибут к методу, который содержит исключения `catch` блока.</span><span class="sxs-lookup"><span data-stu-id="51ddb-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="51ddb-137">Этот элемент конфигурации, доступны только в .NET Framework 4 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="51ddb-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51ddb-138">Пример</span><span class="sxs-lookup"><span data-stu-id="51ddb-138">Example</span></span>  
 <span data-ttu-id="51ddb-139">В следующем примере показано, как указать, что приложение следует вернуться к поведению до .NET Framework 4 и перехватить все сбои поврежденного состояния исключения.</span><span class="sxs-lookup"><span data-stu-id="51ddb-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="51ddb-140">См. также</span><span class="sxs-lookup"><span data-stu-id="51ddb-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="51ddb-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="51ddb-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="51ddb-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="51ddb-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

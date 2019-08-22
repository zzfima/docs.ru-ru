---
title: Элемент <legacyCorruptedStateExceptionsPolicy>
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2715548a40579375cebbdd5fb9003738a42ff714
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663656"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a><span data-ttu-id="00f0e-102">\<Элемент > Легацикорруптедстатиксцептионсполици</span><span class="sxs-lookup"><span data-stu-id="00f0e-102">\<legacyCorruptedStateExceptionsPolicy> Element</span></span>
<span data-ttu-id="00f0e-103">Указывает, позволяет ли среда CLR использовать управляемый код для перехвата нарушений доступа и других исключений поврежденного состояния.</span><span class="sxs-lookup"><span data-stu-id="00f0e-103">Specifies whether the common language runtime allows managed code to catch access violations and other corrupted state exceptions.</span></span>  
  
 <span data-ttu-id="00f0e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="00f0e-104">\<configuration></span></span>  
<span data-ttu-id="00f0e-105">\<> среды выполнения</span><span class="sxs-lookup"><span data-stu-id="00f0e-105">\<runtime></span></span>  
<span data-ttu-id="00f0e-106">\<Легацикорруптедстатиксцептионсполици ></span><span class="sxs-lookup"><span data-stu-id="00f0e-106">\<legacyCorruptedStateExceptionsPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00f0e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00f0e-107">Syntax</span></span>  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="00f0e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="00f0e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="00f0e-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="00f0e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="00f0e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="00f0e-110">Attributes</span></span>  
  
|<span data-ttu-id="00f0e-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="00f0e-111">Attribute</span></span>|<span data-ttu-id="00f0e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="00f0e-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="00f0e-113">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="00f0e-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="00f0e-114">Указывает, что приложение будет перехватывать сбои исключения состояния, такие как нарушения прав доступа.</span><span class="sxs-lookup"><span data-stu-id="00f0e-114">Specifies that the application will catch corrupting state exception failures such as access violations.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="00f0e-115">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="00f0e-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="00f0e-116">Значение</span><span class="sxs-lookup"><span data-stu-id="00f0e-116">Value</span></span>|<span data-ttu-id="00f0e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="00f0e-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="00f0e-118">Приложение не будет перехватывать сбои повреждения состояния, такие как нарушения прав доступа.</span><span class="sxs-lookup"><span data-stu-id="00f0e-118">The application will not catch corrupting state exception failures such as access violations.</span></span> <span data-ttu-id="00f0e-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00f0e-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="00f0e-120">Приложение будет перехватывать сбои исключения состояния, такие как нарушения прав доступа.</span><span class="sxs-lookup"><span data-stu-id="00f0e-120">The application will catch corrupting state exception failures such as access violations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="00f0e-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="00f0e-121">Child Elements</span></span>  
 <span data-ttu-id="00f0e-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="00f0e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="00f0e-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="00f0e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="00f0e-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="00f0e-124">Element</span></span>|<span data-ttu-id="00f0e-125">Описание</span><span class="sxs-lookup"><span data-stu-id="00f0e-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="00f0e-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="00f0e-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="00f0e-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="00f0e-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00f0e-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="00f0e-128">Remarks</span></span>  
 <span data-ttu-id="00f0e-129">В .NET Framework версии 3,5 и более ранних версиях среда CLR позволяла управляемому коду перехватывать исключения, которые были вызваны поврежденными состояниями процессов.</span><span class="sxs-lookup"><span data-stu-id="00f0e-129">In the .NET Framework version 3.5 and earlier, the common language runtime allowed managed code to catch exceptions that were raised by corrupted process states.</span></span> <span data-ttu-id="00f0e-130">Нарушение прав доступа — это пример исключения этого типа.</span><span class="sxs-lookup"><span data-stu-id="00f0e-130">An access violation is an example of this type of exception.</span></span>  
  
 <span data-ttu-id="00f0e-131">Начиная с .NET Framework 4 управляемый код больше не перехватывает исключения этих типов в `catch` блоках.</span><span class="sxs-lookup"><span data-stu-id="00f0e-131">Starting with the .NET Framework 4, managed code no longer catches these types of exceptions in `catch` blocks.</span></span> <span data-ttu-id="00f0e-132">Однако это изменение можно переопределить и обрабатывать исключения поврежденного состояния двумя способами:</span><span class="sxs-lookup"><span data-stu-id="00f0e-132">However, you can override this change and maintain the handling of corrupted state exceptions in two ways:</span></span>  
  
- <span data-ttu-id="00f0e-133">`enabled` Задайте для `<legacyCorruptedStateExceptionsPolicy>` атрибута`true`элемента значение.</span><span class="sxs-lookup"><span data-stu-id="00f0e-133">Set the `<legacyCorruptedStateExceptionsPolicy>` element's `enabled` attribute to `true`.</span></span> <span data-ttu-id="00f0e-134">Этот параметр конфигурации применяется процессвиде и влияет на все методы.</span><span class="sxs-lookup"><span data-stu-id="00f0e-134">This configuration setting is applied processwide and affects all methods.</span></span>  
  
 <span data-ttu-id="00f0e-135">-или-</span><span class="sxs-lookup"><span data-stu-id="00f0e-135">-or-</span></span>  
  
- <span data-ttu-id="00f0e-136">Примените `catch` атрибут к методу, содержащему блок исключений. <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="00f0e-136">Apply the <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> attribute to the method that contains the exceptions `catch` block.</span></span>  
  
 <span data-ttu-id="00f0e-137">Этот элемент конфигурации доступен только в .NET Framework 4 и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="00f0e-137">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f0e-138">Пример</span><span class="sxs-lookup"><span data-stu-id="00f0e-138">Example</span></span>  
 <span data-ttu-id="00f0e-139">В следующем примере показано, как указать, что приложение должно вернуться к поведению до .NET Framework 4, и перехватить все сбои исключений состояния.</span><span class="sxs-lookup"><span data-stu-id="00f0e-139">The following example shows how to specify that the application should revert to the behavior before the .NET Framework 4, and catch all corrupting state exception failures.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="00f0e-140">См. также</span><span class="sxs-lookup"><span data-stu-id="00f0e-140">See also</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [<span data-ttu-id="00f0e-141">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="00f0e-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="00f0e-142">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="00f0e-142">Configuration File Schema</span></span>](../index.md)

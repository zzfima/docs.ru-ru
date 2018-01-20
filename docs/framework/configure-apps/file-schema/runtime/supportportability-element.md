---
title: "&lt;supportPortability&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- supportPortability element
- <supportPortability> element
ms.assetid: 6453ef66-19b4-41f3-b712-52d0c2abc9ca
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 52ef9cce9ee28c6329f688bb9ac751f0f9016657
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltsupportportabilitygt-element"></a><span data-ttu-id="0da15-102">&lt;supportPortability&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="0da15-102">&lt;supportPortability&gt; Element</span></span>
<span data-ttu-id="0da15-103">Указывает, что приложение может ссылаться на ту же сборку в двух различных реализациях .NET Framework, отключая поведение по умолчанию, которое рассматривает сборки как эквивалент для переносимости приложения.</span><span class="sxs-lookup"><span data-stu-id="0da15-103">Specifies that an application can reference the same assembly in two different implementations of the .NET Framework, by disabling the default behavior that treats the assemblies as equivalent for application portability purposes.</span></span>  
  
 <span data-ttu-id="0da15-104">\<Конфигурация > элемент</span><span class="sxs-lookup"><span data-stu-id="0da15-104">\<configuration> Element</span></span>  
<span data-ttu-id="0da15-105">\<Среда выполнения > элемент</span><span class="sxs-lookup"><span data-stu-id="0da15-105">\<runtime> Element</span></span>  
<span data-ttu-id="0da15-106">\<assemblyBinding > элемент</span><span class="sxs-lookup"><span data-stu-id="0da15-106">\<assemblyBinding> Element</span></span>  
<span data-ttu-id="0da15-107">\<supportPortability > элемент</span><span class="sxs-lookup"><span data-stu-id="0da15-107">\<supportPortability> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da15-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0da15-108">Syntax</span></span>  
  
```xml  
<supportPortability PKT="public_key_token" enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0da15-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0da15-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0da15-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0da15-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0da15-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0da15-111">Attributes</span></span>  
  
|<span data-ttu-id="0da15-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0da15-112">Attribute</span></span>|<span data-ttu-id="0da15-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="0da15-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0da15-114">PKT</span><span class="sxs-lookup"><span data-stu-id="0da15-114">PKT</span></span>|<span data-ttu-id="0da15-115">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0da15-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="0da15-116">Указывает токен открытого ключа затронутых сборки в виде строки.</span><span class="sxs-lookup"><span data-stu-id="0da15-116">Specifies the public key token of the affected assembly, as a string.</span></span>|  
|<span data-ttu-id="0da15-117">enabled</span><span class="sxs-lookup"><span data-stu-id="0da15-117">enabled</span></span>|<span data-ttu-id="0da15-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="0da15-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0da15-119">Указывает, следует ли включить поддержку переносимости между реализациями заданной сборки платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0da15-119">Specifies whether support for portability between implementations of the specified .NET Framework assembly should be enabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0da15-120">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="0da15-120">enabled Attribute</span></span>  
  
|<span data-ttu-id="0da15-121">Значение</span><span class="sxs-lookup"><span data-stu-id="0da15-121">Value</span></span>|<span data-ttu-id="0da15-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="0da15-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0da15-123">true</span><span class="sxs-lookup"><span data-stu-id="0da15-123">true</span></span>|<span data-ttu-id="0da15-124">Включите поддержку переносимости между реализациями заданной сборки платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0da15-124">Enable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="0da15-125">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0da15-125">This is the default.</span></span>|  
|<span data-ttu-id="0da15-126">False</span><span class="sxs-lookup"><span data-stu-id="0da15-126">false</span></span>|<span data-ttu-id="0da15-127">Отключите поддержку переносимости между реализациями заданной сборки платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0da15-127">Disable support for portability between implementations of the specified .NET Framework assembly.</span></span> <span data-ttu-id="0da15-128">Это позволяет приложению иметь ссылки на несколько реализаций указанной сборки.</span><span class="sxs-lookup"><span data-stu-id="0da15-128">This enables the application to have references to multiple implementations of the specified assembly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0da15-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0da15-129">Child Elements</span></span>  
 <span data-ttu-id="0da15-130">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0da15-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0da15-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0da15-131">Parent Elements</span></span>  
  
|<span data-ttu-id="0da15-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="0da15-132">Element</span></span>|<span data-ttu-id="0da15-133">Описание:</span><span class="sxs-lookup"><span data-stu-id="0da15-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0da15-134">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0da15-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0da15-135">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="0da15-135">Contains information about assembly binding and garbage collection.</span></span>|  
|`assemblyBinding`|<span data-ttu-id="0da15-136">Содержит сведения о перенаправлении версии сборки и о расположениях сборок.</span><span class="sxs-lookup"><span data-stu-id="0da15-136">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0da15-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="0da15-137">Remarks</span></span>  
 <span data-ttu-id="0da15-138">Начиная с версии [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], автоматически обеспечивается для приложений, которые можно использовать любой из двух реализации платформы .NET Framework, например реализации .NET Framework или .NET Framework для Silverlight реализации.</span><span class="sxs-lookup"><span data-stu-id="0da15-138">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], support is automatically provided for applications that can use either of two implementations of the .NET Framework, for example either the .NET Framework implementation or the .NET Framework for Silverlight implementation.</span></span> <span data-ttu-id="0da15-139">Две реализации определенной сборки .NET Framework рассматриваются как эквивалент связывателя сборок.</span><span class="sxs-lookup"><span data-stu-id="0da15-139">The two implementations of a particular .NET Framework assembly are seen as equivalent by the assembly binder.</span></span> <span data-ttu-id="0da15-140">В нескольких сценариях эта функция переносимости приложений вызывает проблемы.</span><span class="sxs-lookup"><span data-stu-id="0da15-140">In a few scenarios, this application portability feature causes problems.</span></span> <span data-ttu-id="0da15-141">В этих сценариях `<supportPortability>` элемент может использоваться, чтобы отключить эту функцию.</span><span class="sxs-lookup"><span data-stu-id="0da15-141">In those scenarios, the `<supportPortability>` element can be used to disable the feature.</span></span>  
  
 <span data-ttu-id="0da15-142">Одним из таких сценариев — это сборка, имеется ссылка в реализации .NET Framework и платформе .NET Framework для Silverlight определенной ссылочной сборки реализации.</span><span class="sxs-lookup"><span data-stu-id="0da15-142">One such scenario is an assembly that has to reference both the .NET Framework implementation and the .NET Framework for Silverlight implementation of a particular reference assembly.</span></span> <span data-ttu-id="0da15-143">Например конструктор XAML, записанных в Windows Presentation Foundation (WPF) может потребоваться эталонной реализации обоих WPF Desktop, пользовательский интерфейс конструктора и подмножество WPF, включенный в реализации Silverlight.</span><span class="sxs-lookup"><span data-stu-id="0da15-143">For example, a XAML designer written in Windows Presentation Foundation (WPF) might need to reference both the WPF Desktop implementation, for the designer's user interface, and the subset of WPF that is included in the Silverlight implementation.</span></span> <span data-ttu-id="0da15-144">По умолчанию отдельные ссылки вызывают ошибку компиляции, так как привязка сборки видит две эквивалентные сборки.</span><span class="sxs-lookup"><span data-stu-id="0da15-144">By default, the separate references cause a compiler error, because assembly binding sees the two assemblies as equivalent.</span></span> <span data-ttu-id="0da15-145">Этот элемент отключает поведение по умолчанию и разрешает завершить компиляцию.</span><span class="sxs-lookup"><span data-stu-id="0da15-145">This element disables the default behavior, and allows compilation to succeed.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0da15-146">Чтобы компилятор для передачи сведений в логику привязки сборки среды CLR, необходимо использовать `/appconfig` параметр компилятора для указания расположения файла app.config, содержащего этот элемент.</span><span class="sxs-lookup"><span data-stu-id="0da15-146">In order for the compiler to pass the information to the common language runtime's assembly-binding logic, you must use the `/appconfig` compiler option to specify the location of the app.config file that contains this element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0da15-147">Пример</span><span class="sxs-lookup"><span data-stu-id="0da15-147">Example</span></span>  
 <span data-ttu-id="0da15-148">Следующий пример позволяет приложению иметь ссылки на реализации .NET Framework и платформе .NET Framework для Silverlight реализации любой сборки .NET Framework, существует в обоих реализациях.</span><span class="sxs-lookup"><span data-stu-id="0da15-148">The following example enables an application to have references to both the .NET Framework implementation and the .NET Framework for Silverlight implementation of any .NET Framework assembly that exists in both implementations.</span></span> <span data-ttu-id="0da15-149">`/appconfig` Необходимо использовать параметр компилятора для указания расположения этого файла app.config.</span><span class="sxs-lookup"><span data-stu-id="0da15-149">The `/appconfig` compiler option must be used to specify the location of this app.config file.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding>  
         <supportPortability PKT="7cec85d7bea7798e" enable="false"/>  
         <supportPortability PKT="31bf3856ad364e35" enable="false"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0da15-150">См. также</span><span class="sxs-lookup"><span data-stu-id="0da15-150">See Also</span></span>  
 [<span data-ttu-id="0da15-151">/ appconfig (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="0da15-151">/appconfig (C# Compiler Options)</span></span>](http://msdn.microsoft.com/library/ee523958.aspx)  
 [<span data-ttu-id="0da15-152">Общие сведения о унификации сборок .NET framework</span><span class="sxs-lookup"><span data-stu-id="0da15-152">.NET Framework Assembly Unification Overview</span></span>](http://msdn.microsoft.com/library/8d8cc65e-031d-463b-bde3-2c6dc2e3bc48)

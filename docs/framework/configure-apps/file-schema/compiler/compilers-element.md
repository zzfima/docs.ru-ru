---
title: Элемент <compilers>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
ms.openlocfilehash: 53dc67d0046ef2f184535f373c5bf19c484c505a
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664322"
---
# <a name="compilers-element"></a><span data-ttu-id="59087-102">\<Компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="59087-102">\<compilers> Element</span></span>
<span data-ttu-id="59087-103">Контейнер для элементов конфигурации компилятора; содержит ноль элементов [\<compiler>](compiler-element.md) или несколько.</span><span class="sxs-lookup"><span data-stu-id="59087-103">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="59087-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="59087-104">\<configuration></span></span>  
<span data-ttu-id="59087-105">\<> System. CodeDom</span><span class="sxs-lookup"><span data-stu-id="59087-105">\<system.codedom></span></span>  
<span data-ttu-id="59087-106">\<Компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="59087-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59087-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59087-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59087-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="59087-108">Attributes and Elements</span></span>  
 <span data-ttu-id="59087-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="59087-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59087-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="59087-110">Attributes</span></span>  
 <span data-ttu-id="59087-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="59087-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59087-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="59087-112">Child Elements</span></span>  
  
|<span data-ttu-id="59087-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="59087-113">Element</span></span>|<span data-ttu-id="59087-114">Описание</span><span class="sxs-lookup"><span data-stu-id="59087-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59087-115">Элемент \<compiler></span><span class="sxs-lookup"><span data-stu-id="59087-115">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="59087-116">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="59087-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59087-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="59087-117">Parent Elements</span></span>  
  
|<span data-ttu-id="59087-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="59087-118">Element</span></span>|<span data-ttu-id="59087-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="59087-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59087-120">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="59087-120">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="59087-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59087-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="59087-122">\<Элемент System. CodeDom ></span><span class="sxs-lookup"><span data-stu-id="59087-122">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="59087-123">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="59087-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59087-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="59087-124">Remarks</span></span>  
 <span data-ttu-id="59087-125">Компилятор > элемент содержит параметры конфигурации компилятора для поставщиков языков на компьютере. [ \<](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="59087-125">The [\<compilers>](compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="59087-126">Каждый элемент > компилятора задает атрибуты конфигурации компилятора для конкретного поставщика языка. [ \<](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="59087-126">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="59087-127">.NET Framework определяет начальные параметры компилятора и языка в файле конфигурации компьютера (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="59087-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="59087-128">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="59087-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="59087-129">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="59087-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="59087-130">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="59087-130">Configuration File</span></span>  
 <span data-ttu-id="59087-131">Этот элемент можно использовать в файле конфигурации компьютера и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="59087-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59087-132">Пример</span><span class="sxs-lookup"><span data-stu-id="59087-132">Example</span></span>  
 <span data-ttu-id="59087-133">В приведенном ниже примере показан типичный элемент конфигурации компилятора.</span><span class="sxs-lookup"><span data-stu-id="59087-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler   
          language="c#;cs;csharp"   
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""    
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59087-134">См. также</span><span class="sxs-lookup"><span data-stu-id="59087-134">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="59087-135">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="59087-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="59087-136">Схема параметров компилятора и поставщика языков</span><span class="sxs-lookup"><span data-stu-id="59087-136">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="59087-137">Элемент \<compiler></span><span class="sxs-lookup"><span data-stu-id="59087-137">\<compiler> Element</span></span>](compiler-element.md)

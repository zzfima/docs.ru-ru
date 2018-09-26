---
title: '&lt;компиляторы&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compilers
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers
helpviewer_keywords:
- compiler configuration elements, <compilers> element
- <compilers> element
- compilers element
ms.assetid: d40fba59-98f9-4783-ae0c-2ebea27ce77b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8ce303d33a83d972247609e5d02d16a4a57669ff
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47083798"
---
# <a name="ltcompilersgt-element"></a><span data-ttu-id="d66f6-102">&lt;компиляторы&gt; элемент</span><span class="sxs-lookup"><span data-stu-id="d66f6-102">&lt;compilers&gt; Element</span></span>
<span data-ttu-id="d66f6-103">Контейнер для элементов конфигурации компилятора; содержит ноль элементов [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) или несколько.</span><span class="sxs-lookup"><span data-stu-id="d66f6-103">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>  
  
 <span data-ttu-id="d66f6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d66f6-104">\<configuration></span></span>  
<span data-ttu-id="d66f6-105">\<System.CodeDom ></span><span class="sxs-lookup"><span data-stu-id="d66f6-105">\<system.codedom></span></span>  
<span data-ttu-id="d66f6-106">\<компиляторы > элемент</span><span class="sxs-lookup"><span data-stu-id="d66f6-106">\<compilers> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d66f6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d66f6-107">Syntax</span></span>  
  
```xml  
<compilers>  
  <compiler ... />  
</compilers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d66f6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d66f6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d66f6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d66f6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d66f6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d66f6-110">Attributes</span></span>  
 <span data-ttu-id="d66f6-111">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d66f6-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d66f6-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d66f6-112">Child Elements</span></span>  
  
|<span data-ttu-id="d66f6-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="d66f6-113">Element</span></span>|<span data-ttu-id="d66f6-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d66f6-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d66f6-115">Элемент \<compiler></span><span class="sxs-lookup"><span data-stu-id="d66f6-115">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="d66f6-116">Задает атрибуты конфигурации компилятора для поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="d66f6-116">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d66f6-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d66f6-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d66f6-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="d66f6-118">Element</span></span>|<span data-ttu-id="d66f6-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d66f6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d66f6-120">Элемент \<configuration></span><span class="sxs-lookup"><span data-stu-id="d66f6-120">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="d66f6-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d66f6-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="d66f6-122">\<System.CodeDom > элемент</span><span class="sxs-lookup"><span data-stu-id="d66f6-122">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="d66f6-123">Задает параметры конфигурации компилятора для доступных поставщиков языков.</span><span class="sxs-lookup"><span data-stu-id="d66f6-123">Specifies compiler configuration settings for available language providers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d66f6-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="d66f6-124">Remarks</span></span>  
 <span data-ttu-id="d66f6-125">[ \<Компиляторы >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) элемент содержит параметры конфигурации компилятора для поставщиков языков на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d66f6-125">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="d66f6-126">Каждый [ \<компилятора >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) элемент задает атрибуты конфигурации компилятора для конкретного поставщика языка.</span><span class="sxs-lookup"><span data-stu-id="d66f6-126">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="d66f6-127">.NET Framework определяет начальной компилятора и языковые параметры поставщика в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="d66f6-127">The .NET Framework defines the initial compiler and language provider settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="d66f6-128">Разработчики и поставщики компиляторов могут добавлять параметры конфигурации для новой реализации <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d66f6-128">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="d66f6-129">С помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> можно осуществлять программное перечисление параметров конфигурации для поставщиков языков и компиляторов на компьютере.</span><span class="sxs-lookup"><span data-stu-id="d66f6-129">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="d66f6-130">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="d66f6-130">Configuration File</span></span>  
 <span data-ttu-id="d66f6-131">Этот элемент может использоваться в файле конфигурации компьютера и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="d66f6-131">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d66f6-132">Пример</span><span class="sxs-lookup"><span data-stu-id="d66f6-132">Example</span></span>  
 <span data-ttu-id="d66f6-133">В приведенном ниже примере показан типичный элемент конфигурации компилятора.</span><span class="sxs-lookup"><span data-stu-id="d66f6-133">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d66f6-134">См. также</span><span class="sxs-lookup"><span data-stu-id="d66f6-134">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="d66f6-135">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="d66f6-135">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="d66f6-136">Схема параметров компилятора и поставщика языков</span><span class="sxs-lookup"><span data-stu-id="d66f6-136">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)  
 [<span data-ttu-id="d66f6-137">Элемент \<compiler></span><span class="sxs-lookup"><span data-stu-id="d66f6-137">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)

---
title: Блоки скриптов с использованием msxsl:script
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: fde6f43f-c594-486f-abcb-2211197fae20
ms.openlocfilehash: a63452df16e452a90eff3977ac8726cc0a5ac439
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710197"
---
# <a name="script-blocks-using-msxslscript"></a><span data-ttu-id="25d48-102">Блоки скриптов с использованием msxsl:script</span><span class="sxs-lookup"><span data-stu-id="25d48-102">Script Blocks Using msxsl:script</span></span>
<span data-ttu-id="25d48-103">Класс <xref:System.Xml.Xsl.XslCompiledTransform> поддерживает внедренные скрипты с помощью элемента `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="25d48-103">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports embedded scripts using the `msxsl:script` element.</span></span> <span data-ttu-id="25d48-104">После загрузки таблицы стилей все определенные функции компилируются в MSIL с помощью модели CodeDOM и выполняются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="25d48-104">When the style sheet is loaded, any defined functions are compiled to Microsoft intermediate language (MSIL) by the Code Document Object Model (CodeDOM) and are executed during run time.</span></span> <span data-ttu-id="25d48-105">Сборка, создаваемая из блока внедренного скрипта, располагается отдельно от сборки, создаваемой для таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="25d48-105">The assembly generated from the embedded script block is separate than the assembly generated for the style sheet.</span></span>  
  
## <a name="enable-xslt-script"></a><span data-ttu-id="25d48-106">Включение скрипта XSLT</span><span class="sxs-lookup"><span data-stu-id="25d48-106">Enable XSLT Script</span></span>  
 <span data-ttu-id="25d48-107">Поддержка внедренных скриптов является необязательным параметром XSLT в классе <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="25d48-107">Support for embedded scripts is an optional XSLT setting on the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="25d48-108">По умолчанию поддержка скриптов отключена.</span><span class="sxs-lookup"><span data-stu-id="25d48-108">Script support is disabled by default.</span></span> <span data-ttu-id="25d48-109">Чтобы включить поддержку скриптов, создайте объект <xref:System.Xml.Xsl.XsltSettings> со значением свойства <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A>, равным `true`, и передайте его методу <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.</span><span class="sxs-lookup"><span data-stu-id="25d48-109">To enable script support, create an <xref:System.Xml.Xsl.XsltSettings> object with the <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A> property set to `true` and pass the object to the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25d48-110">Скрипты XSLT следует включать только при необходимости в поддержке скриптов и при работе в полностью доверенной среде.</span><span class="sxs-lookup"><span data-stu-id="25d48-110">XSLT scripting should be enabled only if you require script support and you are working in a fully trusted environment.</span></span>  
  
## <a name="msxslscript-element-definition"></a><span data-ttu-id="25d48-111">Определение элемента msxsl:script</span><span class="sxs-lookup"><span data-stu-id="25d48-111">msxsl:script Element Definition</span></span>  
 <span data-ttu-id="25d48-112">Элемент `msxsl:script` введен корпорацией Майкрософт в качестве расширения рекомендации XSLT 1.0 и имеет следующее определение:</span><span class="sxs-lookup"><span data-stu-id="25d48-112">The `msxsl:script` element is a Microsoft extension to the XSLT 1.0 recommendation and has the following definition:</span></span>  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 <span data-ttu-id="25d48-113">Префикс `msxsl` привязан к URI-коду пространства имен `urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="25d48-113">The `msxsl` prefix is bound to the `urn:schemas-microsoft-com:xslt` namespace URI.</span></span> <span data-ttu-id="25d48-114">Таблица стилей должна содержать декларацию пространства имен `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.</span><span class="sxs-lookup"><span data-stu-id="25d48-114">The style sheet must include the `xmlns:msxsl=urn:schemas-microsoft-com:xslt` namespace declaration.</span></span>  
  
 <span data-ttu-id="25d48-115">Атрибут `language` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="25d48-115">The `language` attribute is optional.</span></span> <span data-ttu-id="25d48-116">Его значением является язык кода внедренного блока.</span><span class="sxs-lookup"><span data-stu-id="25d48-116">Its value is the code language of the embedded code block.</span></span> <span data-ttu-id="25d48-117">Язык сопоставляется с необходимым компилятором CodeDOM с помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="25d48-117">The language is mapped to the appropriate CodeDOM compiler using the <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="25d48-118">Класс <xref:System.Xml.Xsl.XslCompiledTransform> может поддерживать любой язык платформы Microsoft .NET при условии, что на компьютере установлен соответствующий поставщик, зарегистрированный в разделе system.codedom файла machine.config.</span><span class="sxs-lookup"><span data-stu-id="25d48-118">The <xref:System.Xml.Xsl.XslCompiledTransform> class can support any Microsoft .NET language, assuming the appropriate provider is installed on the machine and is registered in the system.codedom section of the machine.config file.</span></span> <span data-ttu-id="25d48-119">Если атрибут `language` не задан, по умолчанию используется язык JScript.</span><span class="sxs-lookup"><span data-stu-id="25d48-119">If a `language` attribute is not specified, the language defaults to JScript.</span></span> <span data-ttu-id="25d48-120">В имени языка не учитывается регистр, поэтому имена «JavaScript» и «javascript» будут эквивалентны.</span><span class="sxs-lookup"><span data-stu-id="25d48-120">The language name is not case-sensitive so 'JavaScript' and 'javascript' are equivalent.</span></span>  
  
 <span data-ttu-id="25d48-121">Атрибут `implements-prefix` обязателен.</span><span class="sxs-lookup"><span data-stu-id="25d48-121">The `implements-prefix` attribute is mandatory.</span></span> <span data-ttu-id="25d48-122">Этот атрибут используется для объявления пространства имен и связывания его с блоком скрипта.</span><span class="sxs-lookup"><span data-stu-id="25d48-122">This attribute is used to declare a namespace and associate it with the script block.</span></span> <span data-ttu-id="25d48-123">Значением этого атрибута является префикс, соответствующий пространству имен.</span><span class="sxs-lookup"><span data-stu-id="25d48-123">The value of this attribute is the prefix that represents the namespace.</span></span> <span data-ttu-id="25d48-124">Этот префикс может определяться в таблице стилей.</span><span class="sxs-lookup"><span data-stu-id="25d48-124">This prefix can be defined somewhere in a style sheet.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="25d48-125">Если используется элемент `msxsl:script`, то настоятельно рекомендуется поместить скрипт (независимо от языка) в раздел CDATA.</span><span class="sxs-lookup"><span data-stu-id="25d48-125">When using the `msxsl:script` element, we strongly recommend that the script, regardless of language, be placed inside a CDATA section.</span></span> <span data-ttu-id="25d48-126">Поскольку скрипт может содержать операторы, идентификаторы или разделители на заданном языке, то, если его поместить вне раздела CDATA, существует возможность, что код скрипта будет ошибочно обработан как XML-код.</span><span class="sxs-lookup"><span data-stu-id="25d48-126">Because the script can contain operators, identifiers, or delimiters for a given language, if it is not contained within a CDATA section, it has the potential of being misinterpreted as XML.</span></span> <span data-ttu-id="25d48-127">В следующем XML-коде показан шаблон раздела CDATA, куда можно поместить код.</span><span class="sxs-lookup"><span data-stu-id="25d48-127">The following XML shows a template of the CDATA section where code can be placed.</span></span>  
  
```xml  
<msxsl:script implements-prefix='your-prefix' language='CSharp'>  
<![CDATA[  
// Code block.  
]]>  
</msxsl:script>  
```  
  
## <a name="script-functions"></a><span data-ttu-id="25d48-128">Функции в скриптах</span><span class="sxs-lookup"><span data-stu-id="25d48-128">Script Functions</span></span>  
 <span data-ttu-id="25d48-129">Функции можно объявлять внутри элемента `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="25d48-129">Functions can be declared within the `msxsl:script` element.</span></span> <span data-ttu-id="25d48-130">При объявлении функции она заключается в блок скрипта.</span><span class="sxs-lookup"><span data-stu-id="25d48-130">When a function is declared, it is contained in a script block.</span></span> <span data-ttu-id="25d48-131">Таблицы стилей могут содержать несколько блоков скриптов, каждый из которых работает независимо от других.</span><span class="sxs-lookup"><span data-stu-id="25d48-131">Style sheets can contain multiple script blocks, each operating independent of the other.</span></span> <span data-ttu-id="25d48-132">Это значит, что в одном блоке скрипта нельзя вызвать функцию, определенную в другом блоке, если в них не объявлены одно и то же пространство имен и один и тот же язык скрипта.</span><span class="sxs-lookup"><span data-stu-id="25d48-132">That means that if you are executing inside a script block, you cannot call a function that you defined in another script block unless it is declared to have the same namespace and the same scripting language.</span></span> <span data-ttu-id="25d48-133">Поскольку каждый блок скрипта может быть написан на собственном языке и блок проходит синтаксический анализ по правилам грамматики этого языка, рекомендуется использовать синтаксис языка, используемого в текущем блоке.</span><span class="sxs-lookup"><span data-stu-id="25d48-133">Because each script block can be in its own language, and the block is parsed according to the grammar rules of that language parser we recommend that you use the correct syntax for the language in use.</span></span> <span data-ttu-id="25d48-134">Например, в пределах блока скрипта на языке Microsoft C# используйте синтаксис комментариев C#.</span><span class="sxs-lookup"><span data-stu-id="25d48-134">For example, if you are in a Microsoft C# script block, use the C# comment syntax.</span></span>  
  
 <span data-ttu-id="25d48-135">Передаваемые аргументы и возвращаемые значения функции могут иметь любой тип.</span><span class="sxs-lookup"><span data-stu-id="25d48-135">The supplied arguments and return values to the function can be of any type.</span></span> <span data-ttu-id="25d48-136">Поскольку типы W3C XPath являются подмножеством типов среды CLR, для типов, которые не относятся к XPath, выполняется преобразование типов.</span><span class="sxs-lookup"><span data-stu-id="25d48-136">Because the W3C XPath types are a subset of the common language runtime (CLR) types, type conversion takes place on types that are not considered to be an XPath type.</span></span> <span data-ttu-id="25d48-137">В следующей таблице показано соответствие типов W3C и типов среды CLR.</span><span class="sxs-lookup"><span data-stu-id="25d48-137">The following table shows the corresponding W3C types and the equivalent CLR type.</span></span>  
  
|<span data-ttu-id="25d48-138">Тип W3C</span><span class="sxs-lookup"><span data-stu-id="25d48-138">W3C type</span></span>|<span data-ttu-id="25d48-139">Тип CLR</span><span class="sxs-lookup"><span data-stu-id="25d48-139">CLR type</span></span>|  
|--------------|--------------|  
|`String`|<xref:System.String>|  
|`Boolean`|<xref:System.Boolean>|  
|`Number`|<xref:System.Double>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator>|  
  
 <span data-ttu-id="25d48-140">Числовые типы среды CLR преобразуются в <xref:System.Double>.</span><span class="sxs-lookup"><span data-stu-id="25d48-140">CLR numeric types are converted to <xref:System.Double>.</span></span> <span data-ttu-id="25d48-141">Тип <xref:System.DateTime> преобразуется в тип <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="25d48-141">The <xref:System.DateTime> type is converted to <xref:System.String>.</span></span> <span data-ttu-id="25d48-142">Типы <xref:System.Xml.XPath.IXPathNavigable> преобразуются в типы <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="25d48-142"><xref:System.Xml.XPath.IXPathNavigable> types are converted to <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="25d48-143">**XPathNavigator[]** преобразуется в <xref:System.Xml.XPath.XPathNodeIterator>.</span><span class="sxs-lookup"><span data-stu-id="25d48-143">**XPathNavigator[]** is converted to <xref:System.Xml.XPath.XPathNodeIterator>.</span></span>  
  
 <span data-ttu-id="25d48-144">Все другие типы вызывают ошибку.</span><span class="sxs-lookup"><span data-stu-id="25d48-144">All other types throw an error.</span></span>  
  
### <a name="importing-namespaces-and-assemblies"></a><span data-ttu-id="25d48-145">Импорт пространств имен и сборок</span><span class="sxs-lookup"><span data-stu-id="25d48-145">Importing Namespaces and Assemblies</span></span>  
 <span data-ttu-id="25d48-146">В классе <xref:System.Xml.Xsl.XslCompiledTransform> определяется готовый набор сборок и пространств имен, которые по умолчанию поддерживаются элементом `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="25d48-146">The <xref:System.Xml.Xsl.XslCompiledTransform> class predefines a set of assemblies and namespaces that are supported by default by the `msxsl:script` element.</span></span> <span data-ttu-id="25d48-147">Однако можно использовать классы и элементы из пространства имен, не входящего в стандартный список. Для этого нужно импортировать сборку и пространство имен в блок `msxsl:script`.</span><span class="sxs-lookup"><span data-stu-id="25d48-147">However, you can use classes and members belonging to a namespace that is not on the predefined list by importing the assembly and namespace in `msxsl:script` block.</span></span>  
  
#### <a name="assemblies"></a><span data-ttu-id="25d48-148">Сборки</span><span class="sxs-lookup"><span data-stu-id="25d48-148">Assemblies</span></span>  
 <span data-ttu-id="25d48-149">По умолчанию создаются ссылки на следующие сборки:</span><span class="sxs-lookup"><span data-stu-id="25d48-149">The following two assemblies are referenced by default:</span></span>  
  
- <span data-ttu-id="25d48-150">System.dll</span><span class="sxs-lookup"><span data-stu-id="25d48-150">System.dll</span></span>  
  
- <span data-ttu-id="25d48-151">System.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="25d48-151">System.Xml.dll</span></span>  
  
- <span data-ttu-id="25d48-152">Microsoft.VisualBasic.dll (если языком скрипта является VB).</span><span class="sxs-lookup"><span data-stu-id="25d48-152">Microsoft.VisualBasic.dll (when the script language is VB)</span></span>  
  
 <span data-ttu-id="25d48-153">Дополнительные сборки можно импортировать с помощью элемента `msxsl:assembly`.</span><span class="sxs-lookup"><span data-stu-id="25d48-153">You can import the additional assemblies using the `msxsl:assembly` element.</span></span> <span data-ttu-id="25d48-154">Таким образом, сборка включается после компиляции таблицы стилей.</span><span class="sxs-lookup"><span data-stu-id="25d48-154">This includes the assembly when the style sheet is compiled.</span></span> <span data-ttu-id="25d48-155">Элемент `msxsl:assembly` имеет следующее определение:</span><span class="sxs-lookup"><span data-stu-id="25d48-155">The `msxsl:assembly` element has the following definition:</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:assembly name="system.assemblyName" />  
  <msxsl:assembly href="path-name" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
 <span data-ttu-id="25d48-156">Атрибут `name` содержит имя сборки, а атрибут `href` - путь к сборке.</span><span class="sxs-lookup"><span data-stu-id="25d48-156">The `name` attribute contains the name of the assembly and the `href` attribute contains the path to the assembly.</span></span> <span data-ttu-id="25d48-157">Имя сборки может быть полным, таким как «System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089», или кратким, таким как «System.Web».</span><span class="sxs-lookup"><span data-stu-id="25d48-157">The assembly name can be a full name, such as "System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089", or a short name, such as "System.Web".</span></span>  
  
#### <a name="namespaces"></a><span data-ttu-id="25d48-158">Пространства имен</span><span class="sxs-lookup"><span data-stu-id="25d48-158">Namespaces</span></span>  
 <span data-ttu-id="25d48-159">По умолчанию включаются следующие пространства имен:</span><span class="sxs-lookup"><span data-stu-id="25d48-159">The following namespaces are included by default:</span></span>  
  
- <span data-ttu-id="25d48-160">System</span><span class="sxs-lookup"><span data-stu-id="25d48-160">System</span></span>  
  
- <span data-ttu-id="25d48-161">System.Collection</span><span class="sxs-lookup"><span data-stu-id="25d48-161">System.Collection</span></span>  
  
- <span data-ttu-id="25d48-162">System.Text</span><span class="sxs-lookup"><span data-stu-id="25d48-162">System.Text</span></span>  
  
- <span data-ttu-id="25d48-163">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="25d48-163">System.Text.RegularExpressions</span></span>  
  
- <span data-ttu-id="25d48-164">System.Xml</span><span class="sxs-lookup"><span data-stu-id="25d48-164">System.Xml</span></span>  
  
- <span data-ttu-id="25d48-165">System.Xml.Xsl;</span><span class="sxs-lookup"><span data-stu-id="25d48-165">System.Xml.Xsl</span></span>  
  
- <span data-ttu-id="25d48-166">System.Xml.XPath</span><span class="sxs-lookup"><span data-stu-id="25d48-166">System.Xml.XPath</span></span>  
  
- <span data-ttu-id="25d48-167">Microsoft.VisualBasic (если языком скрипта является VB).</span><span class="sxs-lookup"><span data-stu-id="25d48-167">Microsoft.VisualBasic (when the script language is VB)</span></span>  
  
 <span data-ttu-id="25d48-168">Можно добавить поддержку дополнительных пространств имен с помощью атрибута `namespace`.</span><span class="sxs-lookup"><span data-stu-id="25d48-168">You can add support for additional namespaces using the `namespace` attribute.</span></span> <span data-ttu-id="25d48-169">Значением атрибута является имя пространства имен.</span><span class="sxs-lookup"><span data-stu-id="25d48-169">The attribute value is the name of the namespace.</span></span>  
  
```xml  
<msxsl:script>  
  <msxsl:using namespace="system.namespaceName" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
## <a name="example"></a><span data-ttu-id="25d48-170">Пример</span><span class="sxs-lookup"><span data-stu-id="25d48-170">Example</span></span>  
 <span data-ttu-id="25d48-171">В следующем примере используется внедренный скрипт для вычисления длины окружности по заданному радиусу.</span><span class="sxs-lookup"><span data-stu-id="25d48-171">The following example uses an embedded script to calculate the circumference of a circle given its radius.</span></span>  
  
 [!code-csharp[XSLT_Script#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Script/CS/xslt_script.cs#1)]
 [!code-vb[XSLT_Script#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Script/VB/xslt_script.vb#1)]  
  
#### <a name="numberxml"></a><span data-ttu-id="25d48-172">number.xml</span><span class="sxs-lookup"><span data-stu-id="25d48-172">number.xml</span></span>  
 [!code-xml[XSLT_Script#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/number.xml#2)]  
  
#### <a name="calcxsl"></a><span data-ttu-id="25d48-173">calc.xsl</span><span class="sxs-lookup"><span data-stu-id="25d48-173">calc.xsl</span></span>  
 [!code-xml[XSLT_Script#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/calc.xsl#3)]  
  
### <a name="output"></a><span data-ttu-id="25d48-174">Вывод</span><span class="sxs-lookup"><span data-stu-id="25d48-174">Output</span></span>  
  
```xml  
<circles xmlns:msxsl="urn:schemas-microsoft-com:xslt" xmlns:user="urn:my-scripts">  
  <circle>  
    <radius>12</radius>  
    <circumference>75.36</circumference>  
  </circle>  
  <circle>  
    <radius>37.5</radius>  
    <circumference>235.5</circumference>  
  </circle>  
</circles>  
```  
  
## <a name="see-also"></a><span data-ttu-id="25d48-175">См. также:</span><span class="sxs-lookup"><span data-stu-id="25d48-175">See also</span></span>

- [<span data-ttu-id="25d48-176">Преобразования XSLT</span><span class="sxs-lookup"><span data-stu-id="25d48-176">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)
- [<span data-ttu-id="25d48-177">Динамическое создание и компиляция исходного кода</span><span class="sxs-lookup"><span data-stu-id="25d48-177">Dynamic Source Code Generation and Compilation</span></span>](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)

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
# <a name="script-blocks-using-msxslscript"></a>Блоки скриптов с использованием msxsl:script
Класс <xref:System.Xml.Xsl.XslCompiledTransform> поддерживает внедренные скрипты с помощью элемента `msxsl:script`. После загрузки таблицы стилей все определенные функции компилируются в MSIL с помощью модели CodeDOM и выполняются во время выполнения. Сборка, создаваемая из блока внедренного скрипта, располагается отдельно от сборки, создаваемой для таблицы стилей.  
  
## <a name="enable-xslt-script"></a>Включение скрипта XSLT  
 Поддержка внедренных скриптов является необязательным параметром XSLT в классе <xref:System.Xml.Xsl.XslCompiledTransform>. По умолчанию поддержка скриптов отключена. Чтобы включить поддержку скриптов, создайте объект <xref:System.Xml.Xsl.XsltSettings> со значением свойства <xref:System.Xml.Xsl.XsltSettings.EnableScript%2A>, равным `true`, и передайте его методу <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A>.  
  
> [!NOTE]
> Скрипты XSLT следует включать только при необходимости в поддержке скриптов и при работе в полностью доверенной среде.  
  
## <a name="msxslscript-element-definition"></a>Определение элемента msxsl:script  
 Элемент `msxsl:script` введен корпорацией Майкрософт в качестве расширения рекомендации XSLT 1.0 и имеет следующее определение:  
  
```xml  
<msxsl:script language = "language-name" implements-prefix = "prefix of user namespace"> </msxsl:script>  
```  
  
 Префикс `msxsl` привязан к URI-коду пространства имен `urn:schemas-microsoft-com:xslt`. Таблица стилей должна содержать декларацию пространства имен `xmlns:msxsl=urn:schemas-microsoft-com:xslt`.  
  
 Атрибут `language` является необязательным. Его значением является язык кода внедренного блока. Язык сопоставляется с необходимым компилятором CodeDOM с помощью метода <xref:System.CodeDom.Compiler.CodeDomProvider.CreateProvider%2A?displayProperty=nameWithType>. Класс <xref:System.Xml.Xsl.XslCompiledTransform> может поддерживать любой язык платформы Microsoft .NET при условии, что на компьютере установлен соответствующий поставщик, зарегистрированный в разделе system.codedom файла machine.config. Если атрибут `language` не задан, по умолчанию используется язык JScript. В имени языка не учитывается регистр, поэтому имена «JavaScript» и «javascript» будут эквивалентны.  
  
 Атрибут `implements-prefix` обязателен. Этот атрибут используется для объявления пространства имен и связывания его с блоком скрипта. Значением этого атрибута является префикс, соответствующий пространству имен. Этот префикс может определяться в таблице стилей.  
  
> [!NOTE]
> Если используется элемент `msxsl:script`, то настоятельно рекомендуется поместить скрипт (независимо от языка) в раздел CDATA. Поскольку скрипт может содержать операторы, идентификаторы или разделители на заданном языке, то, если его поместить вне раздела CDATA, существует возможность, что код скрипта будет ошибочно обработан как XML-код. В следующем XML-коде показан шаблон раздела CDATA, куда можно поместить код.  
  
```xml  
<msxsl:script implements-prefix='your-prefix' language='CSharp'>  
<![CDATA[  
// Code block.  
]]>  
</msxsl:script>  
```  
  
## <a name="script-functions"></a>Функции в скриптах  
 Функции можно объявлять внутри элемента `msxsl:script`. При объявлении функции она заключается в блок скрипта. Таблицы стилей могут содержать несколько блоков скриптов, каждый из которых работает независимо от других. Это значит, что в одном блоке скрипта нельзя вызвать функцию, определенную в другом блоке, если в них не объявлены одно и то же пространство имен и один и тот же язык скрипта. Поскольку каждый блок скрипта может быть написан на собственном языке и блок проходит синтаксический анализ по правилам грамматики этого языка, рекомендуется использовать синтаксис языка, используемого в текущем блоке. Например, в пределах блока скрипта на языке Microsoft C# используйте синтаксис комментариев C#.  
  
 Передаваемые аргументы и возвращаемые значения функции могут иметь любой тип. Поскольку типы W3C XPath являются подмножеством типов среды CLR, для типов, которые не относятся к XPath, выполняется преобразование типов. В следующей таблице показано соответствие типов W3C и типов среды CLR.  
  
|Тип W3C|Тип CLR|  
|--------------|--------------|  
|`String`|<xref:System.String>|  
|`Boolean`|<xref:System.Boolean>|  
|`Number`|<xref:System.Double>|  
|`Result Tree Fragment`|<xref:System.Xml.XPath.XPathNavigator>|  
|`Node Set`|<xref:System.Xml.XPath.XPathNodeIterator>|  
  
 Числовые типы среды CLR преобразуются в <xref:System.Double>. Тип <xref:System.DateTime> преобразуется в тип <xref:System.String>. Типы <xref:System.Xml.XPath.IXPathNavigable> преобразуются в типы <xref:System.Xml.XPath.XPathNavigator>. **XPathNavigator[]** преобразуется в <xref:System.Xml.XPath.XPathNodeIterator>.  
  
 Все другие типы вызывают ошибку.  
  
### <a name="importing-namespaces-and-assemblies"></a>Импорт пространств имен и сборок  
 В классе <xref:System.Xml.Xsl.XslCompiledTransform> определяется готовый набор сборок и пространств имен, которые по умолчанию поддерживаются элементом `msxsl:script`. Однако можно использовать классы и элементы из пространства имен, не входящего в стандартный список. Для этого нужно импортировать сборку и пространство имен в блок `msxsl:script`.  
  
#### <a name="assemblies"></a>Сборки  
 По умолчанию создаются ссылки на следующие сборки:  
  
- System.dll  
  
- System.Xml.dll  
  
- Microsoft.VisualBasic.dll (если языком скрипта является VB).  
  
 Дополнительные сборки можно импортировать с помощью элемента `msxsl:assembly`. Таким образом, сборка включается после компиляции таблицы стилей. Элемент `msxsl:assembly` имеет следующее определение:  
  
```xml  
<msxsl:script>  
  <msxsl:assembly name="system.assemblyName" />  
  <msxsl:assembly href="path-name" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
 Атрибут `name` содержит имя сборки, а атрибут `href` - путь к сборке. Имя сборки может быть полным, таким как «System.Data, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b77a5c561934e089», или кратким, таким как «System.Web».  
  
#### <a name="namespaces"></a>Пространства имен  
 По умолчанию включаются следующие пространства имен:  
  
- System  
  
- System.Collection  
  
- System.Text  
  
- System.Text.RegularExpressions  
  
- System.Xml  
  
- System.Xml.Xsl;  
  
- System.Xml.XPath  
  
- Microsoft.VisualBasic (если языком скрипта является VB).  
  
 Можно добавить поддержку дополнительных пространств имен с помощью атрибута `namespace`. Значением атрибута является имя пространства имен.  
  
```xml  
<msxsl:script>  
  <msxsl:using namespace="system.namespaceName" />  
    <![CDATA[  
    // User code  
    ]]>  
</msxsl:script>  
```  
  
## <a name="example"></a>Пример  
 В следующем примере используется внедренный скрипт для вычисления длины окружности по заданному радиусу.  
  
 [!code-csharp[XSLT_Script#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_Script/CS/xslt_script.cs#1)]
 [!code-vb[XSLT_Script#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_Script/VB/xslt_script.vb#1)]  
  
#### <a name="numberxml"></a>number.xml  
 [!code-xml[XSLT_Script#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/number.xml#2)]  
  
#### <a name="calcxsl"></a>calc.xsl  
 [!code-xml[XSLT_Script#3](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_Script/XML/calc.xsl#3)]  
  
### <a name="output"></a>Вывод  
  
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
  
## <a name="see-also"></a>См. также:

- [Преобразования XSLT](../../../../docs/standard/data/xml/xslt-transformations.md)
- [Динамическое создание и компиляция исходного кода](../../../../docs/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation.md)

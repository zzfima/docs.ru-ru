---
title: "&lt;summary&gt; (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "<summary>"
  - "summary"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<summary> - XML-тег C#"
  - "summary - XML-тег C#"
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# &lt;summary&gt; (Руководство по программированию на C#)
## Синтаксис  
  
```  
<summary>description</summary>  
```  
  
#### Параметры  
 `description`  
 Сводка объекта.  
  
## Заметки  
 Тег \<summary\> следует использовать для описания типа или члена типа.  Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks\>](../../../csharp/programming-guide/xmldoc/remarks.md).  Чтобы включить средства документации, такие как [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061), для создания внутренних гиперссылок на страницы документации для элементов кода, используйте атрибут [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md).  
  
 Текст в теге \<summary\> является единственным источником сведений о типе для технологии IntelliSense и также отображается в [Object Browser Window](http://msdn.microsoft.com/ru-ru/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda).  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [\/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md).  Для создания конечной документации на основе созданного компилятором файла можно создать пользовательское средство или использовать такое средство, как [Sandcastle](http://go.microsoft.com/fwlink/?LinkId=124061).  
  
## Пример  
 [!code-cs[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 В предыдущем примере получаются следующие XML\-файл.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## Пример  
 В следующем примере показано, как создать ссылку `cref` на универсальный тип.  
  
 [!code-cs[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 В предыдущем примере получаются следующие XML\-файл.  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
  
```  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
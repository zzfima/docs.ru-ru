---
title: '&lt;summary&gt; (руководство по программированию на C#)'
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 5415603142afaeb5df3f6c2d270a8f895196a207
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359634"
---
# <a name="ltsummarygt-c-programming-guide"></a>&lt;summary&gt; (руководство по программированию на C#)
## <a name="syntax"></a>Синтаксис  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>Параметры  
 `description`  
 Сводка объекта.  
  
## <a name="remarks"></a>Примечания  
 Тег \<summary> следует использовать для описания типа или члена типа. Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md). Чтобы включить средства документации, такие как [Sandcastle](https://github.com/EWSoftware/SHFB), для создания внутренних гиперссылок на страницы документации для элементов кода, используйте атрибут [cref](../../../csharp/programming-guide/xmldoc/cref-attribute.md).  
  
 Текст в теге \<summary> является единственным источником сведений о типе для технологии IntelliSense и также отображается в окне обозревателя объектов.  
  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md). Для создания окончательной документации на основе сформированного компилятором файла можно создать пользовательское средство или использовать такое средство, как [Sandcastle](https://github.com/EWSoftware/SHFB).  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 В предыдущем примере выводится следующий XML-файл.  
  
```xml  
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
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать ссылку `cref` на универсальный тип.  
  
 [!code-csharp[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 В предыдущем примере выводится следующий XML-файл.  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [Рекомендуемые теги для комментариев документации](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

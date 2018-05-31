---
title: Практическое руководство. Использование XML-документации (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: d7f1f51040033cf25f7f1aefb04d249e6e028ca3
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472780"
---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a>Практическое руководство. Использование XML-документации (Руководство по программированию в C#)
В данном примере представлены основные общие сведения о задокументированном типе.  
  
## <a name="example"></a>Пример  
 [!code-csharp[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  

В примере создается XML-файл со следующим содержимым:

```xml  
<?xml version="1.0"?>  
<doc>  
 <assembly>  
 <name>xmlsample</name>  
 </assembly>  
 <members>  
 <member name="T:SomeClass">  
 <summary>  
 Class level summary documentation goes here.</summary>  
 <remarks>  
 Longer comments can be associated with a type or member  
 through the remarks tag</remarks>  
 </member>  
 <member name="F:SomeClass.m_Name">  
 <summary>  
 Store for the name property</summary>  
 </member>  
 <member name="M:SomeClass.#ctor">  
 <summary>The class constructor.</summary>  
 </member>  
 <member name="M:SomeClass.SomeMethod(System.String)">  
 <summary>  
 Description for SomeMethod.</summary>  
 <param name="s"> Parameter description for s goes here</param>  
 <seealso cref="T:System.String">  
 You can use the cref attribute on any tag to reference a type or member  
 and the compiler will check that the reference exists. </seealso>  
 </member>  
 <member name="M:SomeClass.SomeOtherMethod">  
 <summary>  
 Some other method. </summary>  
 <returns>  
 Return results are described through the returns tag.</returns>  
 <seealso cref="M:SomeClass.SomeMethod(System.String)">  
 Notice the use of the cref attribute to reference a specific method </seealso>  
 </member>  
 <member name="M:SomeClass.Main(System.String[])">  
 <summary>  
 The entry point for the application.  
 </summary>  
 <param name="args"> A list of command line arguments</param>  
 </member>  
 <member name="P:SomeClass.Name">  
 <summary>  
 Name property </summary>  
 <value>A value tag is used to describe the property value</value>  
 </member>  
 </members>  
</doc>   
```

## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать этот пример, введите в командной строке:  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 Эта команда создает XML-файл XMLsample.xml, который можно просмотреть в браузере или с помощью команды TYPE.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Документация XML начинается с ///. При создании нового проекта мастер добавляет несколько строк ///. Обработка этих комментариев имеет некоторые ограничения.  
  
-   Документация должна представлять собой XML с правильным форматом. Если формат XML неверен, то выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.  
  
-   Разработчики могут создавать собственные наборы тегов. Существует рекомендуемый набор тегов (см. статью о [рекомендуемых тегах для комментариев документации](recommended-tags-for-documentation-comments.md)). Некоторые рекомендуемые теги имеют особые значения.  
  
    -   Тег \<param> используется для описания параметров. При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации. При сбое проверки компилятор выдает предупреждение.  
  
    -   Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода. Компилятор проверяет наличие этого элемента кода. При сбое проверки компилятор выдает предупреждение. Компилятор учитывает любые операторы `using` при поиске типа, описанного в атрибуте `cref`.  
  
    -   Тег \<summary> используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типе или члене.  
  
        > [!NOTE]
        >  XML-файл не предоставляет полную информацию о типе и членах (например, он не содержит никаких сведений о типе). Чтобы получить полную информацию о типе или члене, необходимо использовать файл документации вместе с отражением на текущий тип или член.  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
 [/doc (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
 [Комментарии XML-документации](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

---
title: "Практическое руководство. Использование XML-документации (руководство по программированию на C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: f4e74e2da4a5f8ba0a9964a5eff4f2a492b8981f
ms.contentlocale: ru-ru
ms.lasthandoff: 05/24/2017

---
# <a name="how-to-use-the-xml-documentation-features-c-programming-guide"></a>Практическое руководство. Использование XML-документации (Руководство по программированию в C#)
В данном примере представлены основные общие сведения о задокументированном типе.  
  
## <a name="example"></a>Пример  
 [!code-cs[csProgGuideDocComments#15](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/how-to-use-the-xml-documentation-features_1.cs)]  
  
 **// Этот XML-файл был создан в предыдущем образце кода.**  
**\<?xml version="1.0"?>**  
**\<doc>**  
 **\<assembly>**  
 **\<name>xmlsample\</name>**  
 **\</assembly>**  
 **\<members>**  
 **\<member name="T:SomeClass">**  
 **\<summary>**  
 **Здесь сводная документация об уровне класса.\</summary>**  
 **\<remarks>**  
 **Расширенные комментарии можно связать с типом или членом**   
 **при помощи тега remarks\</remarks>**  
 **\</member>**  
 **\<member name="F:SomeClass.m_Name">**  
 **\<summary>**  
 **Хранилище для свойства name\</summary>**  
 **\</member>**  
 **\<member name="M:SomeClass.#ctor">**  
 **\<summary>Конструктор класса.\</summary>**   
 **\</member>**  
 **\<member name="M:SomeClass.SomeMethod(System.String)">**  
 **\<summary>**  
 **Описание метода SomeMethod.\</summary>**  
 **\<param name="s"> Здесь описание параметра s\</param>**  
 **\<seealso cref="T:System.String">**  
 **Атрибут cref можно использовать в любом теге для ссылки на тип или член,**   
 **и тогда компилятор проверит существование ссылки. \</seealso>**  
 **\</member>**  
 **\<member name="M:SomeClass.SomeOtherMethod">**  
 **\<summary>**  
 **Какой-либо другой метод. \</summary>**  
 **\<returns>**  
 **Возврат результатов, описанных при помощи тега returns.\</returns>**  
 **\<seealso cref="M:SomeClass.SomeMethod(System.String)">**  
 **Обратите внимание, что атрибут cref используется для ссылки на указанный метод \</seealso>**  
 **\</member>**  
 **\<member name="M:SomeClass.Main(System.String[])">**  
 **\<summary>**  
 **Точка входа для приложения.**  
 **\</summary>**  
 **\<param name="args"> Список аргументов командной строки\</param>**  
 **\</member>**  
 **\<member name="P:SomeClass.Name">**  
 **\<summary>**  
 **Свойство Name \</summary>**  
 **\<value>**  
 **Тег value используется для описания значения свойства\</value>**  
 **\</member>**  
 **\</members>**  
**\</doc>**   
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы скомпилировать этот пример, введите в командной строке:  
  
 `csc XMLsample.cs /doc:XMLsample.xml`  
  
 Эта команда создает XML-файл XMLsample.xml, который можно просмотреть в браузере или с помощью команды TYPE.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Документация XML начинается с ///. При создании нового проекта мастер добавляет несколько строк ///. Обработка этих комментариев имеет некоторые ограничения.  
  
-   Документация должна представлять собой XML с правильным форматом. Если формат XML неверен, то выдается предупреждение и файл документации содержит комментарий о том, что произошла ошибка.  
  
-   Разработчики могут создавать собственные наборы тегов. Однако существует рекомендуемый набор тегов (см. раздел "См. также" в данной теме). Некоторые рекомендуемые теги имеют особые значения.  
  
    -   Тег \<param> используется для описания параметров. При использовании этого тега компилятор проверяет, что параметр существует и все параметры описаны в документации. При сбое проверки компилятор выдает предупреждение.  
  
    -   Атрибут `cref` может быть присоединен к любому тегу для предоставления ссылки на элемент кода. Компилятор проверяет наличие этого элемента кода. При сбое проверки компилятор выдает предупреждение. Компилятор учитывает любые операторы `using` при поиске типа, описанного в атрибуте `cref`.  
  
    -   Тег \<summary> используется технологией IntelliSense в Visual Studio для отображения дополнительных сведений о типе или члене.  
  
        > [!NOTE]
        >  XML-файл не предоставляет полную информацию о типе и членах (например, он не содержит никаких сведений о типе). Чтобы получить полную информацию о типе или члене, необходимо использовать файл документации вместе с отражением на текущий тип или член.  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [/doc (параметры компилятора C#)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)   
 [Комментарии XML-документации](../../../csharp/programming-guide/xmldoc/xml-documentation-comments.md)

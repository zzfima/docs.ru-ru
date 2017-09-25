---
title: "namespace (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- namespace_CSharpKeyword
- namespace
dev_langs:
- CSharp
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
caps.latest.revision: 28
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2cef3949d9a41db36406db059218f7a204172ea
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="namespace-c-reference"></a>namespace (Справочник по C#)
Ключевое слово `namespace` используется для объявления области действия, которая содержит набор связанных объектов. Пространство имен можно использовать для организации элементов кода и для создания глобально уникальных типов.  
  
 [!code-cs[csrefKeywordsNamespace#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_1.cs)]  
  
## <a name="remarks"></a>Примечания  
 В пространстве имен можно объявить один или несколько следующих типов:  
  
-   другое пространство имен  
  
-   [class](../../../csharp/language-reference/keywords/class.md)  
  
-   [interface](../../../csharp/language-reference/keywords/interface.md)  
  
-   [struct](../../../csharp/language-reference/keywords/struct.md)  
  
-   [enum](../../../csharp/language-reference/keywords/enum.md)  
  
-   [delegate](../../../csharp/language-reference/keywords/delegate.md)  
  
 Независимо от того, было ли пространство имен объявлено явным образом в исходном файле на языке C#, компилятор добавляет пространство имен по умолчанию. Это безымянное пространство имен, иногда называемое глобальным пространством имен, существует в каждом файле. Любой идентификатор в глобальном пространстве имен доступен для использования в именованном пространстве имен.  
  
 Пространства имен неявно имеют общий доступ, и это невозможно изменить. Описание модификаторов доступа, которые можно назначить элементам в пространстве имен, см. в разделе [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md).  
  
 Пространство имен можно определить в двух или нескольких объявлениях. Например, в следующем примере два класса определяются в качестве части пространства имен `MyCompany`:  
  
 [!code-cs[csrefKeywordsNamespace#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_2.cs)]  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как можно вызвать статический метод вложенного пространства имен.  
  
 [!code-cs[csrefKeywordsNamespace#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/namespace_3.cs)]  
  
## <a name="for-more-information"></a>Дополнительные сведения  
 Дополнительные сведения об использовании пространств имен см. в следующих разделах:  
  
-   [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)  
  
-   [Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [Практическое руководство. Использование псевдонима глобального пространства имен](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [using](../../../csharp/language-reference/keywords/using.md)


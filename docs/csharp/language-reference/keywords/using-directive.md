---
title: "Директива using (справочник по C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
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
ms.openlocfilehash: e91cc4fea9fbe57b257e17915cd28b3b82f12f6e
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="using-directive-c-reference"></a>Директива using (Справочник по C#)
Директива `using` используется в следующих трех целях.  
  
-   Для разрешения использования типов в пространстве имен, чтобы не нужно было квалифицировать использование типа в этом пространстве имен:  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   Для разрешения доступа к статическим членам типа без необходимости квалификации доступа с помощью имени типа: 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    Дополнительные сведения см. в разделе [Директива using static](using-static.md).

-   Чтобы создать псевдоним для пространства имен или типа. Это называется *директивой using static*.  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 Ключевое слово `using` также используется для создания *операторов using*, которые помогают обеспечить правильную обработку объектов <xref:System.IDisposable>, таких как файлы и шрифты. Дополнительные сведения см. в разделе [Оператор using](../../../csharp/language-reference/keywords/using-statement.md).  
  
## <a name="using-static-type"></a>Использование статического типа  
 Вы можете обращаться к статическим членам типа без необходимости квалификации доступа с помощью имени типа:  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a>Примечания  
 Область директивы `using` ограничена файлом, в котором она находится.  
  
 Создайте псевдоним `using`, чтобы упростить квалификацию идентификатора для пространства имен или типа. Правая часть директивы псевдонима using всегда должна быть полным типом независимо от директив using до нее.  
  
 Создайте директиву `using`, чтобы использовать типы в пространстве имен без необходимости указания этого пространства имен. Директива `using` не предоставляет доступ к пространствам имен, вложенным в указанное пространство имен.  
  
 Пространства имен делятся на две категории: пользовательские и системные. Пользовательские пространства имен задаются в вашем коде. Список системных пространств имен см. в разделе [Библиотека классов .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195).  
  
 Примеры ссылочных методов в других сборках см. в разделе [Создание и использование библиотек DLL C#](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).  
  
## <a name="example-1"></a>Пример 1  
  
 В следующем примере показано, как задать и использовать псевдоним `using` для пространства имен.  
  
 [!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 Псевдоним using не может иметь открытый универсальный тип с правой стороны. Например, нельзя создать псевдоним using для List\<T>, но можно создать его для List\<int>.  
  
## <a name="example-2"></a>Пример 2  
  
 В следующем примере показано, как задать директиву `using` и псевдоним `using` для класса.  
  
 [!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a>Спецификация языка C#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>См. также  
 [Справочник по C#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Использование пространств имен](../../../csharp/programming-guide/namespaces/using-namespaces.md)   
 [Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова, используемые для пространств имен](../../../csharp/language-reference/keywords/namespace-keywords.md)   
 [Пространства имен](../../../csharp/programming-guide/namespaces/index.md)   
 [Оператор using](../../../csharp/language-reference/keywords/using-statement.md)


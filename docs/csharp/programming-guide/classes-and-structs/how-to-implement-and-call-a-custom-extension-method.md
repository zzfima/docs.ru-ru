---
title: "Практическое руководство. Реализация и вызов пользовательского метода расширения (руководство по программированию в C#) | Документы Майкрософт"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
caps.latest.revision: 15
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
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9ba08e55e3bc07c2ce6369e2b33ccbe632545d24
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>Практическое руководство. Реализация и вызов пользовательского метода расширения (Руководство по программированию в C#)
В этом разделе демонстрируется реализация собственных методов расширения для любого типа в [библиотеке классов .NET Framework](http://go.microsoft.com/fwlink/?LinkID=217856), а также любого другого типа .NET, который требуется расширить. Клиентский код может использовать методы расширения путем добавления ссылки на содержащую их библиотеку DLL и добавления директивы [using](../../../csharp/language-reference/keywords/using-directive.md), которая указывает пространство имен, в котором определены методы расширения.  
  
## <a name="to-define-and-call-the-extension-method"></a>Определение и вызов метода расширения  
  
1.  Определите статический [класс](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md), который будет содержать метод расширения.  
  
     Класс должен быть видимым для клиентского кода. Дополнительные сведения о правилах доступа см. в разделах [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
2.  Реализуйте метод расширения как статический метод как минимум с тем же уровнем видимости, что и содержащий класс.  
  
3.  Первый параметр метода указывает тип, с которым работает метод. Ему должен предшествовать модификатор [this](../../../csharp/language-reference/keywords/this.md).  
  
4.  В вызывающем коде добавьте директиву `using`, чтобы задать [пространство имен](../../../csharp/language-reference/keywords/namespace.md), содержащее класс метода расширения.  
  
5.  Вызовите методы, как если бы они являлись методами экземпляра для типа.  
  
     Обратите внимание, что первый параметр не указан вызывающим кодом, поскольку он представляет тип, к которому применяется оператор, и компилятору уже известен тип объекта. Вам необходимо предоставить аргументы только для параметров со 2 по `n`.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере реализуется метод расширения с именем `WordCount` в классе `CustomExtensions.StringExtension`. Метод работает с классом <xref:System.String>класса, который указан как первый параметр метода. Пространство имен `CustomExtensions` импортируется в пространство имен приложения, и метод вызывается внутри метода `Main`.  
  
 [!code-cs[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить этот код, скопируйте и вставьте его в проект консольного приложения Visual C#, созданный в [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)]. По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] и содержит ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq. Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.   
  
## <a name="net-framework-security"></a>Безопасность платформы .NET Framework  
 Методы расширения не предоставляют определенных уязвимостей безопасности. Они не могут использоваться для олицетворения существующих методов для типа, поскольку все конфликты имен разрешаются в пользу метода экземпляра или статического метода, определяемого самим типом. Методы расширения не могут получить доступ к любым конфиденциальным данным в расширенном классе.  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)   
 [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [Встроенный язык запросов LINQ](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)   
 [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)   
 [protected](../../../csharp/language-reference/keywords/protected.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [this](../../../csharp/language-reference/keywords/this.md)   
 [namespace](../../../csharp/language-reference/keywords/namespace.md)

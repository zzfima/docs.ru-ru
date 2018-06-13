---
title: Практическое руководство. Реализация и вызов пользовательского метода расширения (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 62dbbbfb7a63c8fb73661fe7d66e73d0eca73107
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340311"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>Практическое руководство. Реализация и вызов пользовательского метода расширения (Руководство по программированию в C#)
Этот раздел описывает, как реализовать свои методы расширения для любого типа .NET Framework. Клиентский код может использовать методы расширения путем добавления ссылки на содержащую их библиотеку DLL и добавления директивы [using](../../../csharp/language-reference/keywords/using-directive.md), которая указывает пространство имен, в котором определены методы расширения.  
  
## <a name="to-define-and-call-the-extension-method"></a>Определение и вызов метода расширения  
  
1.  Определите статический [класс](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md), который будет содержать метод расширения.  
  
     Класс должен быть видимым для клиентского кода. Дополнительные сведения о правилах доступа см. в разделах [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
2.  Реализуйте метод расширения как статический метод как минимум с тем же уровнем видимости, что и содержащий класс.  
  
3.  Первый параметр метода указывает тип, с которым работает метод. Ему должен предшествовать модификатор [this](../../../csharp/language-reference/keywords/this.md).  
  
4.  В вызывающем коде добавьте директиву `using`, чтобы задать [пространство имен](../../../csharp/language-reference/keywords/namespace.md), содержащее класс метода расширения.  
  
5.  Вызовите методы, как если бы они являлись методами экземпляра для типа.  
  
     Обратите внимание, что первый параметр не указан вызывающим кодом, поскольку он представляет тип, к которому применяется оператор, и компилятору уже известен тип объекта. Вам необходимо предоставить аргументы только для параметров со 2 по `n`.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере реализуется метод расширения с именем `WordCount` в классе `CustomExtensions.StringExtension`. Метод работает с классом <xref:System.String> класса, который указан как первый параметр метода. Пространство имен `CustomExtensions` импортируется в пространство имен приложения, и метод вызывается внутри метода `Main`.  
  
 [!code-csharp[csProgGuideExtensionMethods#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-and-call-a-custom-extension-method_1.cs)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить этот код, скопируйте и вставьте его в проект консольного приложения Visual C#, созданный в Visual Studio. По умолчанию этот проект предназначен для версии 3.5 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] и содержит ссылку на библиотеку System.Core.dll и директиву `using` для пространства имен System.Linq. Если один или несколько из этих обязательных компонентов отсутствуют в проекте, их можно добавить вручную.  
  
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

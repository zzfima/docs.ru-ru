---
title: Как выполнить Руководство по программированию на C#. Реализация и вызов пользовательского метода расширения
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 9f1f7994043288f8896b48a3f12d1c7ee93c3661
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245552"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Реализация и вызов пользовательского метода расширения
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

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Методы расширения](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)  
- [Встроенный язык запросов LINQ](../../../csharp/linq/linq-in-csharp.md)  
- [Статические классы и члены статических классов](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
- [protected](../../../csharp/language-reference/keywords/protected.md)  
- [internal](../../../csharp/language-reference/keywords/internal.md)  
- [public](../../../csharp/language-reference/keywords/public.md)  
- [this](../../../csharp/language-reference/keywords/this.md)  
- [namespace](../../../csharp/language-reference/keywords/namespace.md)

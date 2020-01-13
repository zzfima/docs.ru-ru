---
title: Руководство по программированию на C#. Использование пространств имен
ms.date: 07/20/2015
f1_keywords:
- cs.names
helpviewer_keywords:
- fully qualified names [C#]
- namespaces [C#], how to use
ms.assetid: 1fe8bf39-addc-438a-bd9e-86410e32381d
ms.openlocfilehash: 5193fc7aaae83cbc0c75e81835244eaaaece69a5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75700202"
---
# <a name="using-namespaces-c-programming-guide"></a>Использование пространств имен. (Руководство по программированию в C#)

Пространства имен часто используются в программировании на C# двумя способами. Первый способ — платформа .NET Framework использует пространства имен для упорядочения множества ее классов. Второй способ — объявление собственных пространств имен поможет вам контролировать область имен классов и методов в более крупных проектах.  
  
## <a name="accessing-namespaces"></a>Доступ к пространствам имен

 Большинство приложений на языке C# начинается с раздела директив `using`. В этом разделе перечисляются пространства имен, которые будут часто использоваться приложением, благодаря чему программист может не указывать их полные названия каждый раз, когда вызывается содержащийся в них метод.  
  
 Например, включив строку  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 в начале программы, программист может использовать код  
  
 [!code-csharp[csProgGuide#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#31)]  
  
 вместо следующего кода:  
  
 [!code-csharp[csProgGuide#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/progGuide.cs#30)]  
  
## <a name="namespace-aliases"></a>Псевдонимы пространств имен

 Можно также использовать [директиву `using`](../../language-reference/keywords/using-directive.md) для создания псевдонимов пространства имен. Используйте [квалификатор псевдонима пространства имен `::`](../../language-reference/operators/namespace-alias-qualifier.md) для доступа к членам пространства имен, обозначенного псевдонимом. В следующем примере показано, как создать и использовать псевдоним для пространства имен.
  
[!code-csharp[csProgGuideNamespaces#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#5)]
  
## <a name="using-namespaces-to-control-scope"></a>Использование пространств имен для управления областью действия

 Область действия объявляется с помощью ключевого слова `namespace`. Определяя области действия в проекте, вы можете упорядочивать код и создавать уникальные на глобальном уровне типы. В следующем примере класс `SampleClass` определяется в двух пространствах имен, одно из которых вложено в другое. [Оператор доступа к членам `.`](../../language-reference/operators/member-access-operators.md#member-access-operator-) используется для отличения вызываемого метода.  
  
 [!code-csharp[csProgGuideNamespaces#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#8)]  
  
## <a name="fully-qualified-names"></a>Полные имена

 Пространства имен и типы имеют уникальные названия, которые описываются полными именами, определяющими их место в логической иерархии. Например, инструкция `A.B` указывает, что `A` — это пространство имен или тип, а `B` — вложенный в него элемент.  
  
 В следующем примере показаны вложенные классы и пространства имен. Полное имя каждого элемента указано в комментарии рядом с ним.  
  
 [!code-csharp[csProgGuideNamespaces#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#9)]  
  
 В предыдущем фрагменте кода:  
  
- Пространство имен `N1` является членом глобального пространства имен. Его полное имя: `N1`.  
  
- Пространство имен `N2` является членом пространства имен `N1`. Его полное имя: `N1.N2`.  
  
- Класс `C1` является членом пространства имен `N1`. Его полное имя: `N1.C1`.  
  
- В этом коде имя класса `C2` используется два раза. Тем не менее полные имена являются уникальными. Первый экземпляр `C2` объявляется в классе `C1`. Соответственно, его полное имя: `N1.C1.C2`. Второй экземпляр `C2` объявляется в пространстве имен `N2`. Соответственно, его полное имя: `N1.N2.C2`.  
  
 Используя представленный выше фрагмент кода, вы можете добавить новый элемент класса `C3` в пространство имен `N1.N2`, как показано выше:  
  
 [!code-csharp[csProgGuideNamespaces#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#10)]  
  
 В общем случае следует использовать [квалификатор псевдонима пространства имен `::`](../../language-reference/operators/namespace-alias-qualifier.md) для ссылки на псевдоним пространства имен или `global::` для ссылки на глобальное пространство имен, а также `.` для определения типов или элементов.  
  
 Использование `::` с псевдонимом, ссылающимся на тип вместо пространства имен, будет ошибкой. Пример:  
  
 [!code-csharp[csProgGuideNamespaces#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#11)]  
  
 [!code-csharp[csProgGuideNamespaces#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#12)]  
  
 Помните, что слово `global` не является предопределенным псевдонимом и, соответственно, выражение `global.X` не имеет какого-либо конкретного значения. Конкретное значение будет получено только при его использовании вместе с `::`.  
  
 Если определить псевдоним с именем global, возникнет предупреждение компилятора CS0440. Это связано с тем, что `global::` всегда ссылается на глобальное пространство имен, а не на псевдоним. Например, предупреждение возникнет в следующем случае:  
  
 [!code-csharp[csProgGuideNamespaces#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces2.cs#13)]  
  
 При работе с псевдонимами рекомендуется использовать `::`, поскольку это обеспечивает защиту от случайного определения дополнительных типов. Рассмотрим следующий пример:  
  
 [!code-csharp[csProgGuideNamespaces#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#14)]  
  
 [!code-csharp[csProgGuideNamespaces#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#15)]  
  
 Этот код будет работать, однако если впоследствии определить тип с именем `Alias`, выражение `Alias.` будет связываться с этим типом. Используя выражение `Alias::Exception`, вы гарантируете, что `Alias` будет обрабатываться как псевдоним пространства имен и не будет ошибочно связываться с типом.  

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Пространства имен](./index.md)
- [Оператор .](../../language-reference/operators/member-access-operators.md#member-access-operator-)
- [Оператор ::](../../language-reference/operators/namespace-alias-qualifier.md)
- [Псевдоним extern](../../language-reference/keywords/extern-alias.md)

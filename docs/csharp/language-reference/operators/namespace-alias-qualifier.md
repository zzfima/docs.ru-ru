---
title: Оператор ::. Справочник по C#
ms.date: 08/09/2019
f1_keywords:
- ::_CSharpKeyword
- global_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- namespace alias qualifier [C#]
- namespace [C#]
- global keyword [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: 84c418627462f83630fe5072a0b0e2089f6588f6
ms.sourcegitcommit: 2514f4e3655081dcfe1b22470c0c28500f952c42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/18/2020
ms.locfileid: "79507130"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="43e5b-102">Оператор :: (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="43e5b-102">:: operator (C# reference)</span></span>

<span data-ttu-id="43e5b-103">Используйте квалификатор псевдонима пространства имен `::` для получения доступа к элементам пространства имен, обозначенного псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="43e5b-103">Use the namespace alias qualifier `::` to access a member of an aliased namespace.</span></span> <span data-ttu-id="43e5b-104">Квалификатор `::` используется только между двумя идентификаторами.</span><span class="sxs-lookup"><span data-stu-id="43e5b-104">You can use the `::` qualifier only between two identifiers.</span></span> <span data-ttu-id="43e5b-105">Левый идентификатор может быть любым из следующих псевдонимов:</span><span class="sxs-lookup"><span data-stu-id="43e5b-105">The left-hand identifier can be any of the following aliases:</span></span>

- <span data-ttu-id="43e5b-106">Псевдоним пространства имен, созданный с помощью [директивы псевдонима using](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="43e5b-106">A namespace alias created with a [using alias directive](../keywords/using-directive.md):</span></span>

  ```csharp
  using forwinforms = System.Drawing;
  using forwpf = System.Windows;
  
  public class Converters
  {
      public static forwpf::Point Convert(forwinforms::Point point) => new forwpf::Point(point.X, point.Y);
  }
  ```

- <span data-ttu-id="43e5b-107">[Псевдоним extern](../keywords/extern-alias.md).</span><span class="sxs-lookup"><span data-stu-id="43e5b-107">An [extern alias](../keywords/extern-alias.md).</span></span>
- <span data-ttu-id="43e5b-108">Псевдоним `global`, который является псевдонимом глобального пространства имен.</span><span class="sxs-lookup"><span data-stu-id="43e5b-108">The `global` alias, which is the global namespace alias.</span></span> <span data-ttu-id="43e5b-109">Глобальное пространство имен — это пространство имен, которое содержит пространства имен и типы, не объявленные в именованном пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="43e5b-109">The global namespace is the namespace that contains namespaces and types that are not declared inside a named namespace.</span></span> <span data-ttu-id="43e5b-110">При использовании с квалификатором `::` псевдоним `global` всегда ссылается на глобальное пространство имен, даже если существует определяемый пользователем псевдоним пространства имен `global`.</span><span class="sxs-lookup"><span data-stu-id="43e5b-110">When used with the `::` qualifier, the `global` alias always references the global namespace, even if there is the user-defined `global` namespace alias.</span></span>

  <span data-ttu-id="43e5b-111">В следующем примере используется псевдоним `global` для доступа к пространству имен .NET <xref:System>, которое является элементом глобального пространства имен.</span><span class="sxs-lookup"><span data-stu-id="43e5b-111">The following example uses the `global` alias to access the .NET <xref:System> namespace, which is a member of the global namespace.</span></span> <span data-ttu-id="43e5b-112">Без псевдонима `global` доступ к определяемому пользователем пространству имен `System`, которое является элементом пространства имен `MyCompany.MyProduct`, будет осуществляться следующим образом:</span><span class="sxs-lookup"><span data-stu-id="43e5b-112">Without the `global` alias, the user-defined `System` namespace, which is a member of the `MyCompany.MyProduct` namespace, would be accessed:</span></span>

  ```csharp
  namespace MyCompany.MyProduct.System
  {
      class Program
      {
          static void Main() => global::System.Console.WriteLine("Using global alias");
      }

      class Console
      {
          string Suggestion => "Consider renaming this class";
      }
  }
  ```

  > [!NOTE]
  > <span data-ttu-id="43e5b-113">Ключевое слово `global` является псевдонимом глобального пространства имен, только если оно является левым идентификатором квалификатора `::`.</span><span class="sxs-lookup"><span data-stu-id="43e5b-113">The `global` keyword is the global namespace alias only when it's the left-hand identifier of the `::` qualifier.</span></span>

<span data-ttu-id="43e5b-114">Можно также использовать [маркер `.`](member-access-operators.md#member-access-expression-) для получения доступа к элементам пространства имен, обозначенного псевдонимом.</span><span class="sxs-lookup"><span data-stu-id="43e5b-114">You can also use the [`.` token](member-access-operators.md#member-access-expression-) to access a member of an aliased namespace.</span></span> <span data-ttu-id="43e5b-115">При этом маркер `.` также используется для доступа к элементам типа.</span><span class="sxs-lookup"><span data-stu-id="43e5b-115">However, the `.` token is also used to access a type member.</span></span> <span data-ttu-id="43e5b-116">Квалификатор `::` гарантирует, что его левый идентификатор всегда ссылается на псевдоним пространства имен, даже если существует тип или пространство имен с таким же именем.</span><span class="sxs-lookup"><span data-stu-id="43e5b-116">The `::` qualifier ensures that its left-hand identifier always references a namespace alias, even if there exists a type or namespace with the same name.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="43e5b-117">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="43e5b-117">C# language specification</span></span>

<span data-ttu-id="43e5b-118">Дополнительные сведения см. в описании [квалификаторов псевдонимов пространства имен](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) в [спецификации языка C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="43e5b-118">For more information, see the [Namespace alias qualifiers](~/_csharplang/spec/namespaces.md#namespace-alias-qualifiers) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="43e5b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="43e5b-119">See also</span></span>

- [<span data-ttu-id="43e5b-120">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="43e5b-120">C# reference</span></span>](../index.md)
- [<span data-ttu-id="43e5b-121">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="43e5b-121">C# operators</span></span>](index.md)
- [<span data-ttu-id="43e5b-122">Использование пространств имен</span><span class="sxs-lookup"><span data-stu-id="43e5b-122">Using namespaces</span></span>](../../programming-guide/namespaces/using-namespaces.md)

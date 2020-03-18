---
title: Руководство по программированию на C#. Тестирование на равенство (идентичность) ссылок
ms.date: 07/20/2015
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
ms.openlocfilehash: 77ce2ef0ccf47d619134c120101ba2aa04f485e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75699058"
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a><span data-ttu-id="71e78-102">Руководство по программированию на C#. Тестирование на равенство (идентичность) ссылок</span><span class="sxs-lookup"><span data-stu-id="71e78-102">How to test for reference equality (Identity) (C# Programming Guide)</span></span>
<span data-ttu-id="71e78-103">Вам не требуется реализовывать настраиваемую логику, чтобы обеспечить поддержку проверки ссылок на равенство в типах.</span><span class="sxs-lookup"><span data-stu-id="71e78-103">You do not have to implement any custom logic to support reference equality comparisons in your types.</span></span> <span data-ttu-id="71e78-104">Эту возможность для всех типов реализует метод <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="71e78-104">This functionality is provided for all types by the static <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="71e78-105">В следующем примере показано, как проверить две переменные на *равенство ссылок*, то есть как определить, ссылаются ли они на один и тот же объект в памяти.</span><span class="sxs-lookup"><span data-stu-id="71e78-105">The following example shows how to determine whether two variables have *reference equality*, which means that they refer to the same object in memory.</span></span>  
  
 <span data-ttu-id="71e78-106">В этом примере также показано, почему <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> всегда возвращает `false` для типов значений и почему не следует использовать <xref:System.Object.ReferenceEquals%2A> для проверки строк на равенство.</span><span class="sxs-lookup"><span data-stu-id="71e78-106">The example also shows why <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> always returns `false` for value types and why you should not use  <xref:System.Object.ReferenceEquals%2A> to determine string equality.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71e78-107">Пример</span><span class="sxs-lookup"><span data-stu-id="71e78-107">Example</span></span>  
 [!code-csharp[csProgGuideObjects#90](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#90)]  
  
 <span data-ttu-id="71e78-108">Реализация `Equals` в универсальном базовом классе <xref:System.Object?displayProperty=nameWithType> также выполняет проверку на равенство ссылок, однако использовать такой подход не рекомендуется, поскольку в случае переопределения метода в классе результат может отличаться от ожидаемого.</span><span class="sxs-lookup"><span data-stu-id="71e78-108">The implementation of `Equals` in the <xref:System.Object?displayProperty=nameWithType> universal base class also performs a reference equality check, but it is best not to use this because, if a class happens to override the method, the results might not be what you expect.</span></span> <span data-ttu-id="71e78-109">Это справедливо также для операторов `==` и `!=`.</span><span class="sxs-lookup"><span data-stu-id="71e78-109">The same is true for the `==` and `!=` operators.</span></span> <span data-ttu-id="71e78-110">При работе со ссылочными типами операторы `==` и `!=` по умолчанию выполняют проверку на равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="71e78-110">When they are operating on reference types, the default behavior of `==` and `!=` is to perform a reference equality check.</span></span> <span data-ttu-id="71e78-111">Тем не менее производные классы могут перегружать оператор для проверки на равенство значений.</span><span class="sxs-lookup"><span data-stu-id="71e78-111">However, derived classes can overload the operator to perform a value equality check.</span></span> <span data-ttu-id="71e78-112">Чтобы свести к минимуму вероятность появления ошибки, рекомендуется всегда использовать <xref:System.Object.ReferenceEquals%2A> в тех случаях, когда требуется проверить два объекта на равенство ссылок.</span><span class="sxs-lookup"><span data-stu-id="71e78-112">To minimize the potential for error, it is best to always use <xref:System.Object.ReferenceEquals%2A> when you have to determine whether two objects have reference equality.</span></span>  
  
 <span data-ttu-id="71e78-113">Константные строки в рамках одной сборки всегда интернируются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="71e78-113">Constant strings within the same assembly are always interned by the runtime.</span></span> <span data-ttu-id="71e78-114">Таким образом, всегда присутствует только один экземпляр каждого уникального строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="71e78-114">That is, only one instance of each unique literal string is maintained.</span></span> <span data-ttu-id="71e78-115">Тем не менее во время выполнения не гарантируется интернирование строк, созданных во время выполнения, а также интернирование двух равных константных строк из разных сборок.</span><span class="sxs-lookup"><span data-stu-id="71e78-115">However, the runtime does not guarantee that strings created at runtime are interned, nor does it guarantee that two equal constant strings in different assemblies are interned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71e78-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="71e78-116">See also</span></span>

- [<span data-ttu-id="71e78-117">Сравнения на равенство</span><span class="sxs-lookup"><span data-stu-id="71e78-117">Equality Comparisons</span></span>](./equality-comparisons.md)

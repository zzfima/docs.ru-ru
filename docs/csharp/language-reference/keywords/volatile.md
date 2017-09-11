---
title: "volatile (Справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
dev_langs:
- CSharp
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
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
ms.openlocfilehash: c8f9fba15991197be885a973435089098a57db87
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="volatile-c-reference"></a><span data-ttu-id="0b3c7-102">volatile (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="0b3c7-102">volatile (C# Reference)</span></span>
<span data-ttu-id="0b3c7-103">Ключевое слово `volatile` означает, что поле может изменить несколько потоков, выполняемых одновременно.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="0b3c7-104">Поля, объявленные `volatile`, не участвуют в оптимизации компилятора, предполагающей доступ для одного потока.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="0b3c7-105">Это гарантирует, что в любой момент времени в поле будет содержаться актуальное значение.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="0b3c7-106">Обычно модификатор `volatile` используется для поля, к которому обращаются несколько потоков; при этом для сериализации доступа оператор [lock](../../../csharp/language-reference/keywords/lock-statement.md) не применяется.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="0b3c7-107">Ключевое слово `volatile` может применяться к полям следующих типов:</span><span class="sxs-lookup"><span data-stu-id="0b3c7-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="0b3c7-108">Ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-108">Reference types.</span></span>  
  
-   <span data-ttu-id="0b3c7-109">Типы указателей (в небезопасном контексте).</span><span class="sxs-lookup"><span data-stu-id="0b3c7-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="0b3c7-110">Несмотря на то, что сам указатель может быть изменяемым, объект, на который он указывает, должен быть постоянным.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="0b3c7-111">Другими словами, объявить указатель на изменяемый объект невозможно.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="0b3c7-112">Типы: sbyte, byte, short, ushort, int, uint, char, float и bool.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="0b3c7-113">Тип перечисления с одним из следующих базовых типов: byte, sbyte, short, ushort, int или uint.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="0b3c7-114">Параметры универсального типа называются ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="0b3c7-115"><xref:System.IntPtr> и <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="0b3c7-116">Ключевое слово volatile можно применять только к полям класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="0b3c7-117">Локальные переменные не могут объявляться как `volatile`.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b3c7-118">Пример</span><span class="sxs-lookup"><span data-stu-id="0b3c7-118">Example</span></span>  
 <span data-ttu-id="0b3c7-119">В следующем примере показано, как объявить переменную поля открытого типа `volatile`.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 <span data-ttu-id="0b3c7-120">[!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0b3c7-120">[!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b3c7-121">Пример</span><span class="sxs-lookup"><span data-stu-id="0b3c7-121">Example</span></span>  
 <span data-ttu-id="0b3c7-122">Следующий пример демонстрирует создание вспомогательного или рабочего потока и его применение для выполнения обработки параллельно с обработкой основного потока.</span><span class="sxs-lookup"><span data-stu-id="0b3c7-122">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="0b3c7-123">Дополнительные сведения о многопоточности см. в разделах [Потоки](../../../standard/threading/index.md) и [Потоки](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span><span class="sxs-lookup"><span data-stu-id="0b3c7-123">For background information about multithreading, see [Threading](../../../standard/threading/index.md) and [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="0b3c7-124">[!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="0b3c7-124">[!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="0b3c7-125">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="0b3c7-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b3c7-126">См. также</span><span class="sxs-lookup"><span data-stu-id="0b3c7-126">See Also</span></span>  
 <span data-ttu-id="0b3c7-127">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0b3c7-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0b3c7-128">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0b3c7-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="0b3c7-129">[Ключевые слова в C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="0b3c7-129">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="0b3c7-130">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="0b3c7-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)


---
title: "volatile (Справочник по C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1cefa39313c3c551e8d05fbc31e528b86c6888d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="volatile-c-reference"></a><span data-ttu-id="26a64-102">volatile (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="26a64-102">volatile (C# Reference)</span></span>
<span data-ttu-id="26a64-103">Ключевое слово `volatile` означает, что поле может изменить несколько потоков, выполняемых одновременно.</span><span class="sxs-lookup"><span data-stu-id="26a64-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="26a64-104">Поля, объявленные `volatile`, не участвуют в оптимизации компилятора, предполагающей доступ для одного потока.</span><span class="sxs-lookup"><span data-stu-id="26a64-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="26a64-105">Это гарантирует, что в любой момент времени в поле будет содержаться актуальное значение.</span><span class="sxs-lookup"><span data-stu-id="26a64-105">This ensures that the most up-to-date value is present in the field at all times.</span></span>  
  
 <span data-ttu-id="26a64-106">Обычно модификатор `volatile` используется для поля, к которому обращаются несколько потоков; при этом для сериализации доступа оператор [lock](../../../csharp/language-reference/keywords/lock-statement.md) не применяется.</span><span class="sxs-lookup"><span data-stu-id="26a64-106">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="26a64-107">Ключевое слово `volatile` может применяться к полям следующих типов:</span><span class="sxs-lookup"><span data-stu-id="26a64-107">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="26a64-108">Ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="26a64-108">Reference types.</span></span>  
  
-   <span data-ttu-id="26a64-109">Типы указателей (в небезопасном контексте).</span><span class="sxs-lookup"><span data-stu-id="26a64-109">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="26a64-110">Несмотря на то, что сам указатель может быть изменяемым, объект, на который он указывает, должен быть постоянным.</span><span class="sxs-lookup"><span data-stu-id="26a64-110">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="26a64-111">Другими словами, объявить указатель на изменяемый объект невозможно.</span><span class="sxs-lookup"><span data-stu-id="26a64-111">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="26a64-112">Типы: sbyte, byte, short, ushort, int, uint, char, float и bool.</span><span class="sxs-lookup"><span data-stu-id="26a64-112">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="26a64-113">Тип перечисления с одним из следующих базовых типов: byte, sbyte, short, ushort, int или uint.</span><span class="sxs-lookup"><span data-stu-id="26a64-113">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="26a64-114">Параметры универсального типа называются ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="26a64-114">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="26a64-115"><xref:System.IntPtr> и <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="26a64-115"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="26a64-116">Ключевое слово volatile можно применять только к полям класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="26a64-116">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="26a64-117">Локальные переменные не могут объявляться как `volatile`.</span><span class="sxs-lookup"><span data-stu-id="26a64-117">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26a64-118">Пример</span><span class="sxs-lookup"><span data-stu-id="26a64-118">Example</span></span>  
 <span data-ttu-id="26a64-119">В следующем примере показано, как объявить переменную поля открытого типа `volatile`.</span><span class="sxs-lookup"><span data-stu-id="26a64-119">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="26a64-120">Пример</span><span class="sxs-lookup"><span data-stu-id="26a64-120">Example</span></span>  
 <span data-ttu-id="26a64-121">Следующий пример демонстрирует создание вспомогательного или рабочего потока и его применение для выполнения обработки параллельно с обработкой основного потока.</span><span class="sxs-lookup"><span data-stu-id="26a64-121">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="26a64-122">Дополнительные сведения о многопоточности см. в разделах [Потоки](../../../standard/threading/index.md) и [Потоки](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="26a64-122">For background information about multithreading, see [Threading](../../../standard/threading/index.md) and [Threading](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="26a64-123">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="26a64-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="26a64-124">См. также</span><span class="sxs-lookup"><span data-stu-id="26a64-124">See Also</span></span>  
 [<span data-ttu-id="26a64-125">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="26a64-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="26a64-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="26a64-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="26a64-127">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="26a64-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="26a64-128">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="26a64-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

---
title: volatile (Справочник по C#)
ms.date: 07/20/2015
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: 64bd5ce7d7dfe3265c3c645467493ab7d8792172
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936882"
---
# <a name="volatile-c-reference"></a><span data-ttu-id="8ff6e-102">volatile (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8ff6e-102">volatile (C# Reference)</span></span>
<span data-ttu-id="8ff6e-103">Ключевое слово `volatile` означает, что поле может изменить несколько потоков, выполняемых одновременно.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-103">The `volatile` keyword indicates that a field might be modified by multiple threads that are executing at the same time.</span></span> <span data-ttu-id="8ff6e-104">Поля, объявленные `volatile`, не участвуют в оптимизации компилятора, предполагающей доступ для одного потока.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-104">Fields that are declared `volatile` are not subject to compiler optimizations that assume access by a single thread.</span></span> <span data-ttu-id="8ff6e-105">Эти ограничения гарантируют, что все потоки будут видеть временные записи, выполняемые другим потоком, в порядке выполнения.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-105">These restrictions ensure that all threads will observe volatile writes performed by any other thread in the order in which they were performed.</span></span> <span data-ttu-id="8ff6e-106">Нет никакой гарантии единого общего прядка временных записей во всех потоках выполнения.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-106">There is no guarantee of a single total ordering of volatile writes as seen from all threads of execution.</span></span>  
  
 <span data-ttu-id="8ff6e-107">Обычно модификатор `volatile` используется для поля, к которому обращаются несколько потоков; при этом для сериализации доступа оператор [lock](../../../csharp/language-reference/keywords/lock-statement.md) не применяется.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-107">The `volatile` modifier is usually used for a field that is accessed by multiple threads without using the [lock](../../../csharp/language-reference/keywords/lock-statement.md) statement to serialize access.</span></span>  
  
 <span data-ttu-id="8ff6e-108">Ключевое слово `volatile` может применяться к полям следующих типов:</span><span class="sxs-lookup"><span data-stu-id="8ff6e-108">The `volatile` keyword can be applied to fields of these types:</span></span>  
  
-   <span data-ttu-id="8ff6e-109">Ссылочные типы.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-109">Reference types.</span></span>  
  
-   <span data-ttu-id="8ff6e-110">Типы указателей (в небезопасном контексте).</span><span class="sxs-lookup"><span data-stu-id="8ff6e-110">Pointer types (in an unsafe context).</span></span> <span data-ttu-id="8ff6e-111">Несмотря на то, что сам указатель может быть изменяемым, объект, на который он указывает, должен быть постоянным.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-111">Note that although the pointer itself can be volatile, the object that it points to cannot.</span></span> <span data-ttu-id="8ff6e-112">Другими словами, объявить указатель на изменяемый объект невозможно.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-112">In other words, you cannot declare a "pointer to volatile."</span></span>  
  
-   <span data-ttu-id="8ff6e-113">Типы: sbyte, byte, short, ushort, int, uint, char, float и bool.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-113">Types such as sbyte, byte, short, ushort, int, uint, char, float, and bool.</span></span>  
  
-   <span data-ttu-id="8ff6e-114">Тип перечисления с одним из следующих базовых типов: byte, sbyte, short, ushort, int или uint.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-114">An enum type with one of the following base types: byte, sbyte, short, ushort, int, or uint.</span></span>  
  
-   <span data-ttu-id="8ff6e-115">Параметры универсального типа называются ссылочными типами.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-115">Generic type parameters known to be reference types.</span></span>  
  
-   <span data-ttu-id="8ff6e-116"><xref:System.IntPtr> и <xref:System.UIntPtr>.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-116"><xref:System.IntPtr> and <xref:System.UIntPtr>.</span></span>  
  
 <span data-ttu-id="8ff6e-117">Ключевое слово volatile можно применять только к полям класса или структуры.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-117">The volatile keyword can only be applied to fields of a class or struct.</span></span> <span data-ttu-id="8ff6e-118">Локальные переменные не могут объявляться как `volatile`.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-118">Local variables cannot be declared `volatile`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ff6e-119">Пример</span><span class="sxs-lookup"><span data-stu-id="8ff6e-119">Example</span></span>  
 <span data-ttu-id="8ff6e-120">В следующем примере показано, как объявить переменную поля открытого типа `volatile`.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-120">The following example shows how to declare a public field variable as `volatile`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="8ff6e-121">Пример</span><span class="sxs-lookup"><span data-stu-id="8ff6e-121">Example</span></span>  
 <span data-ttu-id="8ff6e-122">Следующий пример демонстрирует создание вспомогательного или рабочего потока и его применение для выполнения обработки параллельно с обработкой основного потока.</span><span class="sxs-lookup"><span data-stu-id="8ff6e-122">The following example demonstrates how an auxiliary or worker thread can be created and used to perform processing in parallel with that of the primary thread.</span></span> <span data-ttu-id="8ff6e-123">Дополнительные сведения о многопоточности см. в разделах [Управляемая поточность](../../../standard/threading/index.md) и [Работа с потоками (C#)](../../programming-guide/concepts/threading/index.md).</span><span class="sxs-lookup"><span data-stu-id="8ff6e-123">For background information about multithreading, see [Managed Threading](../../../standard/threading/index.md) and [Threading (C#)](../../programming-guide/concepts/threading/index.md).</span></span>  
  
 [!code-csharp[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8ff6e-124">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8ff6e-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ff6e-125">См. также</span><span class="sxs-lookup"><span data-stu-id="8ff6e-125">See Also</span></span>  
 [<span data-ttu-id="8ff6e-126">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8ff6e-126">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8ff6e-127">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8ff6e-127">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8ff6e-128">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="8ff6e-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8ff6e-129">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="8ff6e-129">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

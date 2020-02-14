---
title: moduloObjectHashcode MDA
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), hashcode modulus
- Modulo object hash code
- moduloObjectHashcode MDA
- hashcode modulus
- MDAs (managed debugging assistants), hashcode modulus
- GetHashCode method
- modulus of hashcodes
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
ms.openlocfilehash: 65bbdfec2d7050d1b474a8186a9ea6e9bb93bd9e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216180"
---
# <a name="moduloobjecthashcode-mda"></a><span data-ttu-id="47fa3-102">moduloObjectHashcode MDA</span><span class="sxs-lookup"><span data-stu-id="47fa3-102">moduloObjectHashcode MDA</span></span>
<span data-ttu-id="47fa3-103">Помощник по отладке управляемого кода (MDA) `moduloObjectHashcode` изменяет поведение класса <xref:System.Object> для выполнения операции деления по модулю с хэш-кодом, возвращаемым методом <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="47fa3-103">The `moduloObjectHashcode` managed debugging assistant (MDA) changes the behavior of the <xref:System.Object> class to perform a modulo operation on the hash code returned by the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="47fa3-104">Модуль по умолчанию для этого помощника по отладке управляемого кода равен 1, поэтому <xref:System.Object.GetHashCode%2A> возвращает 0 для всех объектов.</span><span class="sxs-lookup"><span data-stu-id="47fa3-104">The default modulus for this MDA is 1, which causes <xref:System.Object.GetHashCode%2A> to return 0 for all objects.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="47fa3-105">Симптомы</span><span class="sxs-lookup"><span data-stu-id="47fa3-105">Symptoms</span></span>  
 <span data-ttu-id="47fa3-106">После перехода на новую версию общеязыковой среды выполнения (CLR) программа больше не работает должным образом:</span><span class="sxs-lookup"><span data-stu-id="47fa3-106">After moving to a new version of the common language runtime (CLR), a program no longer executes properly:</span></span>  
  
- <span data-ttu-id="47fa3-107">Программа получает неправильный объект из <xref:System.Collections.Hashtable>.</span><span class="sxs-lookup"><span data-stu-id="47fa3-107">The program is getting the wrong object from a <xref:System.Collections.Hashtable>.</span></span>  
  
- <span data-ttu-id="47fa3-108">Изменение порядка перечисления в <xref:System.Collections.Hashtable> приводит к нарушению работы программы.</span><span class="sxs-lookup"><span data-stu-id="47fa3-108">The order of enumeration from a <xref:System.Collections.Hashtable> has a change that breaks the program.</span></span>  
  
- <span data-ttu-id="47fa3-109">Два объекта, которые ранее были равны, больше не равны.</span><span class="sxs-lookup"><span data-stu-id="47fa3-109">Two objects that used to be equal are no longer equal.</span></span>  
  
- <span data-ttu-id="47fa3-110">Два объекта, которые ранее были не равны, теперь равны.</span><span class="sxs-lookup"><span data-stu-id="47fa3-110">Two objects that used to not be equal are now equal.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="47fa3-111">Причина</span><span class="sxs-lookup"><span data-stu-id="47fa3-111">Cause</span></span>  
 <span data-ttu-id="47fa3-112">Программа может получать неверный объект из <xref:System.Collections.Hashtable> из-за реализации метода <xref:System.Object.Equals%2A> в классе для ключа в проверках на равенство для объектов <xref:System.Collections.Hashtable> путем сравнения результатов вызова со значениями, полученными в результате метода <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="47fa3-112">Your program may be getting the wrong object from a <xref:System.Collections.Hashtable> because the implementation of the <xref:System.Object.Equals%2A> method on the class for the key into the <xref:System.Collections.Hashtable> tests for equality of objects by comparing the results of the call to the <xref:System.Object.GetHashCode%2A> method.</span></span> <span data-ttu-id="47fa3-113">Хэш-коды не должны использоваться для проверки равенства объектов, так как два объекта могут иметь одинаковые хэш-коды, даже если соответствующие им поля имеют разные значения.</span><span class="sxs-lookup"><span data-stu-id="47fa3-113">Hash codes should not be used to test for object equality because two objects may have the same hash code even if their respective fields have different values.</span></span> <span data-ttu-id="47fa3-114">Такие конфликты хэш-кодов иногда происходят, хотя и нечасто.</span><span class="sxs-lookup"><span data-stu-id="47fa3-114">These hash code collisions, although rare in practice, do occur.</span></span> <span data-ttu-id="47fa3-115">Из-за таких конфликтов два ключа в запросе <xref:System.Collections.Hashtable>, которые не равны, кажутся равными, и <xref:System.Collections.Hashtable> возвращает неправильный объект.</span><span class="sxs-lookup"><span data-stu-id="47fa3-115">The effect this has on a <xref:System.Collections.Hashtable> lookup is that two keys which are not equal appear to be equal, and the wrong object is returned from the <xref:System.Collections.Hashtable>.</span></span> <span data-ttu-id="47fa3-116">По соображениям производительности реализация <xref:System.Object.GetHashCode%2A> может изменяться в различных версиях среды выполнения. Поэтому конфликты, отсутствующие в одной версии, могут произойти в последующих версиях.</span><span class="sxs-lookup"><span data-stu-id="47fa3-116">For performance reasons, the implementation of <xref:System.Object.GetHashCode%2A> can change between runtime versions, so collisions that might not occur on one version might occur on subsequent versions.</span></span> <span data-ttu-id="47fa3-117">Включите этот помощник по отладке управляемого кода, чтобы проверить, содержит ли ваш код ошибки из-за конфликтов хэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="47fa3-117">Enable this MDA to test whether your code has bugs when hash codes collide.</span></span> <span data-ttu-id="47fa3-118">После включения помощника метод <xref:System.Object.GetHashCode%2A> возвращает 0, что приводит к конфликту всех хэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="47fa3-118">When enabled, this MDA causes the <xref:System.Object.GetHashCode%2A> method to return 0, resulting in all hash codes colliding.</span></span> <span data-ttu-id="47fa3-119">Единственным побочным эффектом отключения этого помощника должно быть замедление работы программы.</span><span class="sxs-lookup"><span data-stu-id="47fa3-119">The only effect enabling this MDA should have on your program is that your program runs slower.</span></span>  
  
 <span data-ttu-id="47fa3-120">Порядок перечисления из <xref:System.Collections.Hashtable> может измениться между различными версиями среды выполнения, если изменяется алгоритм вычисления кэш-кодов.</span><span class="sxs-lookup"><span data-stu-id="47fa3-120">The order of enumeration from a <xref:System.Collections.Hashtable> may change from one version of the runtime to another if the algorithm used to compute the hash codes for the key change.</span></span> <span data-ttu-id="47fa3-121">Чтобы проверить, зависит ли ваша программа от порядка перечисления ключей или значений в хэш-таблице, включите этот помощник по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="47fa3-121">To test whether your program has taken a dependency on the order of enumeration of keys or values out of a hash table, you can enable this MDA.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="47fa3-122">Решение</span><span class="sxs-lookup"><span data-stu-id="47fa3-122">Resolution</span></span>  
 <span data-ttu-id="47fa3-123">Никогда не используйте хэш-коды вместо идентификаторов объектов.</span><span class="sxs-lookup"><span data-stu-id="47fa3-123">Never use hash codes as a substitute for object identity.</span></span> <span data-ttu-id="47fa3-124">Чтобы не сравнивать хэш-коды, переопределите метод <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="47fa3-124">Implement the override of the <xref:System.Object.Equals%2A?displayProperty=nameWithType> method to not compare hash codes.</span></span>  
  
 <span data-ttu-id="47fa3-125">Не следует создавать зависимости от порядка перечисления ключей или значений в хэш-таблицах.</span><span class="sxs-lookup"><span data-stu-id="47fa3-125">Do not create dependencies on the order of enumerations of keys or values in hash tables.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="47fa3-126">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="47fa3-126">Effect on the Runtime</span></span>  
 <span data-ttu-id="47fa3-127">При включении этого помощника по отладке управляемого кода программа может работать медленнее.</span><span class="sxs-lookup"><span data-stu-id="47fa3-127">Applications run more slowly when this MDA is enabled.</span></span> <span data-ttu-id="47fa3-128">Этот помощник просто принимает хэш-код, который был бы возвращен, и вместо него возвращает остаток от деления по модулю.</span><span class="sxs-lookup"><span data-stu-id="47fa3-128">This MDA simply takes the hash code that would have been returned and instead returns the remainder when divided by a modulus.</span></span>  
  
## <a name="output"></a><span data-ttu-id="47fa3-129">Вывод</span><span class="sxs-lookup"><span data-stu-id="47fa3-129">Output</span></span>  
 <span data-ttu-id="47fa3-130">Этот помощник по отладке управляемого кода не выводит никаких данных.</span><span class="sxs-lookup"><span data-stu-id="47fa3-130">There is no output for this MDA.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="47fa3-131">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="47fa3-131">Configuration</span></span>  
 <span data-ttu-id="47fa3-132">Атрибут `modulus` задает модуль, используемый в хэш-коде.</span><span class="sxs-lookup"><span data-stu-id="47fa3-132">The `modulus` attribute specifies the modulus used on the hash code.</span></span> <span data-ttu-id="47fa3-133">Значение по умолчанию ― 1.</span><span class="sxs-lookup"><span data-stu-id="47fa3-133">The default value is 1.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="47fa3-134">См. также:</span><span class="sxs-lookup"><span data-stu-id="47fa3-134">See also</span></span>

- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.Equals%2A?displayProperty=nameWithType>
- [<span data-ttu-id="47fa3-135">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="47fa3-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)

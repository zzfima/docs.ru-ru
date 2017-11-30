---
title: "Создание новых строк в .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d000cd88fc9ee9fd48ef25e9bb4982688564a2a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="70e0b-102">Создание новых строк в .NET</span><span class="sxs-lookup"><span data-stu-id="70e0b-102">Creating New Strings in .NET</span></span>
<span data-ttu-id="70e0b-103">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Позволяет создавать с помощью простого присваивания строки, а также перегружать конструктор класса для создания строк с помощью нескольких различных параметров.</span><span class="sxs-lookup"><span data-stu-id="70e0b-103">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="70e0b-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Также предоставляет несколько методов в <xref:System.String?displayProperty=nameWithType> объектов путем объединения нескольких строк, массивов строк или объектов класса, создать новую строку.</span><span class="sxs-lookup"><span data-stu-id="70e0b-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="70e0b-105">Создание строк с помощью присваивания</span><span class="sxs-lookup"><span data-stu-id="70e0b-105">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="70e0b-106">Самый простой способ создать новый <xref:System.String> объект — присвоить строковый литерал в <xref:System.String> объекта.</span><span class="sxs-lookup"><span data-stu-id="70e0b-106">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="70e0b-107">Создание строк с помощью конструктора класса</span><span class="sxs-lookup"><span data-stu-id="70e0b-107">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="70e0b-108">Можно использовать перегрузки <xref:System.String> конструктор класса для создания строк из массивов знаков.</span><span class="sxs-lookup"><span data-stu-id="70e0b-108">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="70e0b-109">Кроме того, строки можно создавать путем копирования того или иного знака указанное количество раз.</span><span class="sxs-lookup"><span data-stu-id="70e0b-109">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="70e0b-110">Методы, возвращающие строки</span><span class="sxs-lookup"><span data-stu-id="70e0b-110">Methods that Return Strings</span></span>  
 <span data-ttu-id="70e0b-111">В следующей таблице перечислено несколько полезных методов, которые возвращают строковые объекты.</span><span class="sxs-lookup"><span data-stu-id="70e0b-111">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="70e0b-112">Имя метода</span><span class="sxs-lookup"><span data-stu-id="70e0b-112">Method name</span></span>|<span data-ttu-id="70e0b-113">Применение</span><span class="sxs-lookup"><span data-stu-id="70e0b-113">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="70e0b-114">Создание форматированной строки из набора объектов ввода.</span><span class="sxs-lookup"><span data-stu-id="70e0b-114">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="70e0b-115">Создание строк из двух или более строк.</span><span class="sxs-lookup"><span data-stu-id="70e0b-115">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="70e0b-116">Создание новой строки с помощью объединения массива строк.</span><span class="sxs-lookup"><span data-stu-id="70e0b-116">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="70e0b-117">Создание новой строки с помощью вставки строки в указанную позицию существующей строки.</span><span class="sxs-lookup"><span data-stu-id="70e0b-117">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="70e0b-118">Копирование указанных знаков в строке в указанную позицию в массиве символов.</span><span class="sxs-lookup"><span data-stu-id="70e0b-118">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="70e0b-119">Формат</span><span class="sxs-lookup"><span data-stu-id="70e0b-119">Format</span></span>  
 <span data-ttu-id="70e0b-120">Можно использовать **String.Format** метод для создания форматированных строк и соединения строк, представляющих несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="70e0b-120">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="70e0b-121">Этот метод автоматически преобразует в строку любой переданный объект.</span><span class="sxs-lookup"><span data-stu-id="70e0b-121">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="70e0b-122">Например, если приложению необходимо отобразить **Int32** значение и **DateTime** значение для пользователя, легко создается строка для представления этих значений с помощью **формат**метод.</span><span class="sxs-lookup"><span data-stu-id="70e0b-122">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="70e0b-123">Сведения о правилах форматирования, используемых в этом методе, см. в разделе [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="70e0b-123">For information about formatting conventions used with this method, see the section on [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="70e0b-124">В следующем примере используется **формат** метод для создания строки, содержащей целочисленную переменную.</span><span class="sxs-lookup"><span data-stu-id="70e0b-124">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="70e0b-125">В этом примере<xref:System.DateTime.Now%2A?displayProperty=nameWithType> отображает текущую дату и время в соответствии с языком и региональными параметрами, связанный с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="70e0b-125">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="70e0b-126">Concat</span><span class="sxs-lookup"><span data-stu-id="70e0b-126">Concat</span></span>  
 <span data-ttu-id="70e0b-127">**String.Concat** метод может использоваться, чтобы легко создавать новый объект строки из двух или более существующих объектов.</span><span class="sxs-lookup"><span data-stu-id="70e0b-127">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="70e0b-128">Он позволяет использовать независимый от языка способ сцепления строк.</span><span class="sxs-lookup"><span data-stu-id="70e0b-128">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="70e0b-129">Этот метод принимает любой класс, производный от **System.Object**.</span><span class="sxs-lookup"><span data-stu-id="70e0b-129">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="70e0b-130">В следующем примере создается строка из двух существующих объектов строки и символа разделителя.</span><span class="sxs-lookup"><span data-stu-id="70e0b-130">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="70e0b-131">Join</span><span class="sxs-lookup"><span data-stu-id="70e0b-131">Join</span></span>  
 <span data-ttu-id="70e0b-132">**String.Join** метод создает новую строку из массива строк и разделителя строки.</span><span class="sxs-lookup"><span data-stu-id="70e0b-132">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="70e0b-133">Этот метод полезен в случае необходимости сцепления нескольких строк и создания списка, отделенного, например, запятой.</span><span class="sxs-lookup"><span data-stu-id="70e0b-133">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="70e0b-134">В следующем примере используется пробел для привязки массива строк.</span><span class="sxs-lookup"><span data-stu-id="70e0b-134">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="70e0b-135">Insert</span><span class="sxs-lookup"><span data-stu-id="70e0b-135">Insert</span></span>  
 <span data-ttu-id="70e0b-136">**String.Insert** метод создает новую строку с помощью вставки строки в указанной позиции в другую строку.</span><span class="sxs-lookup"><span data-stu-id="70e0b-136">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="70e0b-137">Этот метод использует отсчитываемый от нуля индекс.</span><span class="sxs-lookup"><span data-stu-id="70e0b-137">This method uses a zero-based index.</span></span> <span data-ttu-id="70e0b-138">В следующем примере строка вставляется в пятую позицию индекса `MyString`, и создается новая строка с этим значением.</span><span class="sxs-lookup"><span data-stu-id="70e0b-138">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="70e0b-139">CopyTo</span><span class="sxs-lookup"><span data-stu-id="70e0b-139">CopyTo</span></span>  
 <span data-ttu-id="70e0b-140">**String.CopyTo** метод копирует частей строки в массив символов.</span><span class="sxs-lookup"><span data-stu-id="70e0b-140">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="70e0b-141">Можно указать начальный индекс строки и число копируемых символов.</span><span class="sxs-lookup"><span data-stu-id="70e0b-141">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="70e0b-142">Для копирования этому методу необходимы исходный индекс, массив знаков, индекс назначения и число символов.</span><span class="sxs-lookup"><span data-stu-id="70e0b-142">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="70e0b-143">Все индексы отсчитываются от нуля.</span><span class="sxs-lookup"><span data-stu-id="70e0b-143">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="70e0b-144">В следующем примере используется **CopyTo** метод копируемых символов слова «Hello» из строкового объекта в первую позицию индекса массива знаков.</span><span class="sxs-lookup"><span data-stu-id="70e0b-144">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="70e0b-145">См. также</span><span class="sxs-lookup"><span data-stu-id="70e0b-145">See Also</span></span>  
 [<span data-ttu-id="70e0b-146">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="70e0b-146">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)  
 [<span data-ttu-id="70e0b-147">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="70e0b-147">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)

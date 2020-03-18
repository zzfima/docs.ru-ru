---
title: Создание новых строк в .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: ef65c50111d6ba91ab70d0b9c8cb90c606f9366c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73103821"
---
# <a name="creating-new-strings-in-net"></a><span data-ttu-id="12ba9-102">Создание новых строк в .NET</span><span class="sxs-lookup"><span data-stu-id="12ba9-102">Creating New Strings in .NET</span></span>
<span data-ttu-id="12ba9-103">.NET Framework позволяет создавать строки с помощью простой операции присваивания, а также перегружать конструктор класса для создания строк с помощью различных параметров.</span><span class="sxs-lookup"><span data-stu-id="12ba9-103">The .NET Framework allows strings to be created using simple assignment, and also overloads a class constructor to support string creation using a number of different parameters.</span></span> <span data-ttu-id="12ba9-104">Кроме того, .NET Framework предоставляет в классе <xref:System.String?displayProperty=nameWithType> несколько методов для создания строковых объектов путем объединения строк, массивов строк или объектов.</span><span class="sxs-lookup"><span data-stu-id="12ba9-104">The .NET Framework also provides several methods in the <xref:System.String?displayProperty=nameWithType> class that create new string objects by combining several strings, arrays of strings, or objects.</span></span>  
  
## <a name="creating-strings-using-assignment"></a><span data-ttu-id="12ba9-105">Создание строк с помощью присваивания</span><span class="sxs-lookup"><span data-stu-id="12ba9-105">Creating Strings Using Assignment</span></span>  
 <span data-ttu-id="12ba9-106">Самый простой способ создать объект <xref:System.String> — присвоить строковый литерал объекту <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="12ba9-106">The easiest way to create a new <xref:System.String> object is simply to assign a string literal to a <xref:System.String> object.</span></span>  
  
## <a name="creating-strings-using-a-class-constructor"></a><span data-ttu-id="12ba9-107">Создание строк с помощью конструктора класса</span><span class="sxs-lookup"><span data-stu-id="12ba9-107">Creating Strings Using a Class Constructor</span></span>  
 <span data-ttu-id="12ba9-108">С помощью перегруженного конструктора класса <xref:System.String> можно создавать строки из массивов символов.</span><span class="sxs-lookup"><span data-stu-id="12ba9-108">You can use overloads of the <xref:System.String> class constructor to create strings from character arrays.</span></span> <span data-ttu-id="12ba9-109">Кроме того, строки можно создавать путем копирования того или иного знака указанное количество раз.</span><span class="sxs-lookup"><span data-stu-id="12ba9-109">You can also create a new string by duplicating a particular character a specified number of times.</span></span>  
  
## <a name="methods-that-return-strings"></a><span data-ttu-id="12ba9-110">Методы, возвращающие строки</span><span class="sxs-lookup"><span data-stu-id="12ba9-110">Methods that Return Strings</span></span>  
 <span data-ttu-id="12ba9-111">В следующей таблице перечислено несколько полезных методов, которые возвращают строковые объекты.</span><span class="sxs-lookup"><span data-stu-id="12ba9-111">The following table lists several useful methods that return new string objects.</span></span>  
  
|<span data-ttu-id="12ba9-112">Имя метода</span><span class="sxs-lookup"><span data-stu-id="12ba9-112">Method name</span></span>|<span data-ttu-id="12ba9-113">Использование</span><span class="sxs-lookup"><span data-stu-id="12ba9-113">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|<span data-ttu-id="12ba9-114">Создание форматированной строки из набора объектов ввода.</span><span class="sxs-lookup"><span data-stu-id="12ba9-114">Builds a formatted string from a set of input objects.</span></span>|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|<span data-ttu-id="12ba9-115">Создание строк из двух или более строк.</span><span class="sxs-lookup"><span data-stu-id="12ba9-115">Builds strings from two or more strings.</span></span>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|<span data-ttu-id="12ba9-116">Создание новой строки с помощью объединения массива строк.</span><span class="sxs-lookup"><span data-stu-id="12ba9-116">Builds a new string by combining an array of strings.</span></span>|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|<span data-ttu-id="12ba9-117">Создание новой строки с помощью вставки строки в указанную позицию существующей строки.</span><span class="sxs-lookup"><span data-stu-id="12ba9-117">Builds a new string by inserting a string into the specified index of an existing string.</span></span>|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|<span data-ttu-id="12ba9-118">Копирование указанных знаков в строке в указанную позицию в массиве символов.</span><span class="sxs-lookup"><span data-stu-id="12ba9-118">Copies specified characters in a string into a specified position in an array of characters.</span></span>|  
  
### <a name="format"></a><span data-ttu-id="12ba9-119">Формат</span><span class="sxs-lookup"><span data-stu-id="12ba9-119">Format</span></span>  
 <span data-ttu-id="12ba9-120">Метод **String.Format** позволяет создавать форматированные строки и сцеплять строки, представляющие несколько объектов.</span><span class="sxs-lookup"><span data-stu-id="12ba9-120">You can use the **String.Format** method to create formatted strings and concatenate strings representing multiple objects.</span></span> <span data-ttu-id="12ba9-121">Этот метод автоматически преобразует в строку любой переданный объект.</span><span class="sxs-lookup"><span data-stu-id="12ba9-121">This method automatically converts any passed object into a string.</span></span> <span data-ttu-id="12ba9-122">Например, если приложение должно предоставить пользователю значение **Int32** и значение **DateTime**, с помощью метода **Format** вы можете соединить их в одну строку для отображения.</span><span class="sxs-lookup"><span data-stu-id="12ba9-122">For example, if your application must display an **Int32** value and a **DateTime** value to the user, you can easily construct a string to represent these values using the **Format** method.</span></span> <span data-ttu-id="12ba9-123">Сведения о правилах форматирования, используемых в этом методе, см. в разделе [Составное форматирование](../../../docs/standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="12ba9-123">For information about formatting conventions used with this method, see the section on [composite formatting](../../../docs/standard/base-types/composite-formatting.md).</span></span>  
  
 <span data-ttu-id="12ba9-124">В следующем примере метод **Format** используется для создания строки, содержащей целочисленную переменную.</span><span class="sxs-lookup"><span data-stu-id="12ba9-124">The following example uses the **Format** method to create a string that uses an integer variable.</span></span>  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 <span data-ttu-id="12ba9-125">В этом примере <xref:System.DateTime.Now%2A?displayProperty=nameWithType> выводит текущую дату и время с учетом языка и региональных параметров, связанных с текущим потоком.</span><span class="sxs-lookup"><span data-stu-id="12ba9-125">In this example,<xref:System.DateTime.Now%2A?displayProperty=nameWithType> displays the current date and time in a manner specified by the culture associated with the current thread.</span></span>  
  
### <a name="concat"></a><span data-ttu-id="12ba9-126">Concat</span><span class="sxs-lookup"><span data-stu-id="12ba9-126">Concat</span></span>  
 <span data-ttu-id="12ba9-127">Метод **String.Concat** позволяет легко создать новый строковый объект из двух или более существующих объектов.</span><span class="sxs-lookup"><span data-stu-id="12ba9-127">The **String.Concat** method can be used to easily create a new string object from two or more existing objects.</span></span> <span data-ttu-id="12ba9-128">Он позволяет использовать независимый от языка способ сцепления строк.</span><span class="sxs-lookup"><span data-stu-id="12ba9-128">It provides a language-independent way to concatenate strings.</span></span> <span data-ttu-id="12ba9-129">Этот метод принимает любой класс, производный от **System.Object**.</span><span class="sxs-lookup"><span data-stu-id="12ba9-129">This method accepts any class that derives from **System.Object**.</span></span> <span data-ttu-id="12ba9-130">В следующем примере создается строка из двух существующих объектов строки и символа разделителя.</span><span class="sxs-lookup"><span data-stu-id="12ba9-130">The following example creates a string from two existing string objects and a separating character.</span></span>  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a><span data-ttu-id="12ba9-131">Join</span><span class="sxs-lookup"><span data-stu-id="12ba9-131">Join</span></span>  
 <span data-ttu-id="12ba9-132">Метод **String.Join** создает строку из массива строк и разделительной строки.</span><span class="sxs-lookup"><span data-stu-id="12ba9-132">The **String.Join** method creates a new string from an array of strings and a separator string.</span></span> <span data-ttu-id="12ba9-133">Этот метод полезен в случае необходимости сцепления нескольких строк и создания списка, отделенного, например, запятой.</span><span class="sxs-lookup"><span data-stu-id="12ba9-133">This method is useful if you want to concatenate multiple strings together, making a list perhaps separated by a comma.</span></span>  
  
 <span data-ttu-id="12ba9-134">В следующем примере используется пробел для привязки массива строк.</span><span class="sxs-lookup"><span data-stu-id="12ba9-134">The following example uses a space to bind a string array.</span></span>  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a><span data-ttu-id="12ba9-135">Вставить</span><span class="sxs-lookup"><span data-stu-id="12ba9-135">Insert</span></span>  
 <span data-ttu-id="12ba9-136">Метод **String.Insert** создает новую строку, вставляя предоставленную строку в указанную позицию в другой строке.</span><span class="sxs-lookup"><span data-stu-id="12ba9-136">The **String.Insert** method creates a new string by inserting a string into a specified position in another string.</span></span> <span data-ttu-id="12ba9-137">Этот метод использует отсчитываемый от нуля индекс.</span><span class="sxs-lookup"><span data-stu-id="12ba9-137">This method uses a zero-based index.</span></span> <span data-ttu-id="12ba9-138">В следующем примере строка вставляется в пятую позицию индекса `MyString`, и создается новая строка с этим значением.</span><span class="sxs-lookup"><span data-stu-id="12ba9-138">The following example inserts a string into the fifth index position of `MyString` and creates a new string with this value.</span></span>  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a><span data-ttu-id="12ba9-139">CopyTo</span><span class="sxs-lookup"><span data-stu-id="12ba9-139">CopyTo</span></span>  
 <span data-ttu-id="12ba9-140">Метод **String.CopyTo** копирует элементы строки в массив символов.</span><span class="sxs-lookup"><span data-stu-id="12ba9-140">The **String.CopyTo** method copies portions of a string into an array of characters.</span></span> <span data-ttu-id="12ba9-141">Можно указать начальный индекс строки и число копируемых символов.</span><span class="sxs-lookup"><span data-stu-id="12ba9-141">You can specify both the beginning index of the string and the number of characters to be copied.</span></span> <span data-ttu-id="12ba9-142">Для копирования этому методу необходимы исходный индекс, массив знаков, индекс назначения и число символов.</span><span class="sxs-lookup"><span data-stu-id="12ba9-142">This method takes the source index, an array of characters, the destination index, and the number of characters to copy.</span></span> <span data-ttu-id="12ba9-143">Все индексы отсчитываются от нуля.</span><span class="sxs-lookup"><span data-stu-id="12ba9-143">All indexes are zero-based.</span></span>  
  
 <span data-ttu-id="12ba9-144">В следующем примере мы используем метод **CopyTo**, чтобы скопировать символы слова Hello из строкового объекта в позицию первого индекса в массиве символов.</span><span class="sxs-lookup"><span data-stu-id="12ba9-144">The following example uses the **CopyTo** method to copy the characters of the word "Hello" from a string object to the first index position of an array of characters.</span></span>  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="12ba9-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="12ba9-145">See also</span></span>

- [<span data-ttu-id="12ba9-146">Базовые операции со строками в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="12ba9-146">Basic String Operations</span></span>](../../../docs/standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="12ba9-147">Составное форматирование</span><span class="sxs-lookup"><span data-stu-id="12ba9-147">Composite Formatting</span></span>](../../../docs/standard/base-types/composite-formatting.md)

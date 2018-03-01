---
title: "Практическое руководство. Отображение миллисекунд в значениях даты и времени"
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
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 552c28420e9a04483b164cfe7e13d942230ec5e0
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a><span data-ttu-id="8f29a-102">Практическое руководство. Отображение миллисекунд в значениях даты и времени</span><span class="sxs-lookup"><span data-stu-id="8f29a-102">How to: Display Milliseconds in Date and Time Values</span></span>
<span data-ttu-id="8f29a-103">Стандартные методы форматирования даты и времени, например <xref:System.DateTime.ToString?displayProperty=nameWithType>, поддерживают часы, минуты и секунды, но не миллисекунды.</span><span class="sxs-lookup"><span data-stu-id="8f29a-103">The default date and time formatting methods, such as <xref:System.DateTime.ToString?displayProperty=nameWithType>, include the hours, minutes, and seconds of a time value but exclude its milliseconds component.</span></span> <span data-ttu-id="8f29a-104">В этом разделе показано, как включить компонент миллисекунд даты и времени в форматированные строки даты и времени.</span><span class="sxs-lookup"><span data-stu-id="8f29a-104">This topic shows how to include a date and time's millisecond component in formatted date and time strings.</span></span>  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a><span data-ttu-id="8f29a-105">Отображение компонента миллисекунд для значения DateTime</span><span class="sxs-lookup"><span data-stu-id="8f29a-105">To display the millisecond component of a DateTime value</span></span>  
  
1.  <span data-ttu-id="8f29a-106">Если вы работаете со строковым представлением даты, преобразуйте ее в значение типа <xref:System.DateTime> или <xref:System.DateTimeOffset>, используя статичный метод <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> или <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8f29a-106">If you are working with the string representation of a date, convert it to a <xref:System.DateTime> or a <xref:System.DateTimeOffset> value by using the static <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="8f29a-107">Чтобы извлечь строковое представление компонента миллисекунд, вызовите метод <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>или <xref:System.DateTimeOffset.ToString%2A> для значения даты и времени, передав ему в параметре `format` шаблон пользовательского формата `fff` или `FFF`, отдельно или с другим описателем пользовательского формата.</span><span class="sxs-lookup"><span data-stu-id="8f29a-107">To extract the string representation of a time's millisecond component, call the date and time value's <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> or <xref:System.DateTimeOffset.ToString%2A> method, and pass the `fff` or `FFF` custom format pattern either alone or with other custom format specifiers as the `format` parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f29a-108">Пример</span><span class="sxs-lookup"><span data-stu-id="8f29a-108">Example</span></span>  
 <span data-ttu-id="8f29a-109">Этот пример выводит в консоль компонент миллисекунд <xref:System.DateTime> и значение <xref:System.DateTimeOffset>, как отдельно, так и в составе более длинной строки даты и времени.</span><span class="sxs-lookup"><span data-stu-id="8f29a-109">The example displays the millisecond component of a <xref:System.DateTime> and a <xref:System.DateTimeOffset> value to the console, both alone and included in a longer date and time string.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 <span data-ttu-id="8f29a-110">Шаблон формата `fff` содержит конечные нули в значении миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="8f29a-110">The `fff` format pattern includes any trailing zeros in the millisecond value.</span></span> <span data-ttu-id="8f29a-111">Шаблон формата `FFF` запрещает их.</span><span class="sxs-lookup"><span data-stu-id="8f29a-111">The `FFF` format pattern suppresses them.</span></span> <span data-ttu-id="8f29a-112">Эта разница показана в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8f29a-112">The difference is illustrated in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 <span data-ttu-id="8f29a-113">Проблема с определением полного описателя пользовательского формата, содержащего компонент миллисекунд, состоит в том, что он жестко задает формат, который может не соответствовать взаимному расположению элементов времени в текущих региональных параметрах приложения.</span><span class="sxs-lookup"><span data-stu-id="8f29a-113">A problem with defining a complete custom format specifier that includes the millisecond component of a date and time is that it defines a hard-coded format that may not correspond to the arrangement of time elements in the application's current culture.</span></span> <span data-ttu-id="8f29a-114">Вместо этого лучше всего извлечь один из шаблонов отображения даты и времени, определенных текущим объектом языка и региональных параметров <xref:System.Globalization.DateTimeFormatInfo>, а затем изменить его для поддержки миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="8f29a-114">A better alternative is to retrieve one of the date and time display patterns defined by the current culture's <xref:System.Globalization.DateTimeFormatInfo> object and modify it to include milliseconds.</span></span> <span data-ttu-id="8f29a-115">Этот подход также показан в примере.</span><span class="sxs-lookup"><span data-stu-id="8f29a-115">The example also illustrates this approach.</span></span> <span data-ttu-id="8f29a-116">Он извлекает шаблон полного отображения даты и времени для текущих языка и региональных параметров, обратившись к свойству <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType>, а затем добавляет в него пользовательский шаблон `.ffff` после шаблона секунд.</span><span class="sxs-lookup"><span data-stu-id="8f29a-116">It retrieves the current culture's full date and time pattern from the <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> property, and then inserts the custom pattern `.ffff` after its seconds pattern.</span></span> <span data-ttu-id="8f29a-117">Обратите внимание, что в примере используется регулярное выражение для выполнения этой операции в одном методе.</span><span class="sxs-lookup"><span data-stu-id="8f29a-117">Note that the example uses a regular expression to perform this operation in a single method call.</span></span>  
  
 <span data-ttu-id="8f29a-118">Описатель настраиваемого формата также используется для отображения дробной части секунд, отличной от миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="8f29a-118">You can also use a custom format specifier to display a fractional part of seconds other than milliseconds.</span></span> <span data-ttu-id="8f29a-119">Например, описатель пользовательского формата `f` или `F` отображает десятые доли секунды, описатель `ff` или `FF` — сотые доли секунды, а описатель `ffff` или `FFFF` — десятитысячные доли секунды.</span><span class="sxs-lookup"><span data-stu-id="8f29a-119">For example, the `f` or `F` custom format specifier displays tenths of a second, the `ff` or `FF` custom format specifier displays hundredths of a second, and the `ffff` or `FFFF` custom format specifier displays ten thousandths of a second.</span></span> <span data-ttu-id="8f29a-120">Дробные части миллисекунд усекаются, а не округляются в возвращаемой строке.</span><span class="sxs-lookup"><span data-stu-id="8f29a-120">Fractional parts of a millisecond are truncated instead of rounded in the returned string.</span></span> <span data-ttu-id="8f29a-121">Эти описатели формата используются в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8f29a-121">These format specifiers are used in the following example.</span></span>  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  <span data-ttu-id="8f29a-122">Существует возможность отображать малые дробные части секунды, например десятитысячные или стотысячные доли секунды.</span><span class="sxs-lookup"><span data-stu-id="8f29a-122">It is possible to display very small fractional units of a second, such as ten thousandths of a second or hundred-thousandths of a second.</span></span> <span data-ttu-id="8f29a-123">Однако эти значения могут не иметь смысла.</span><span class="sxs-lookup"><span data-stu-id="8f29a-123">However, these values may not be meaningful.</span></span> <span data-ttu-id="8f29a-124">Точность значений даты и времени зависит от разрешения системных часов.</span><span class="sxs-lookup"><span data-stu-id="8f29a-124">The precision of date and time values depends on the resolution of the system clock.</span></span> <span data-ttu-id="8f29a-125">В операционных системах Windows NT, начиная с версии 3.5, и [!INCLUDE[windowsver](../../../includes/windowsver-md.md)], разрешение часов приблизительно соответствует 10–15 миллисекундам.</span><span class="sxs-lookup"><span data-stu-id="8f29a-125">On Windows NT 3.5 and later, and [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] operating systems, the clock's resolution is approximately 10-15 milliseconds.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8f29a-126">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8f29a-126">Compiling the Code</span></span>  
 <span data-ttu-id="8f29a-127">Скомпилируйте код из командной строки с помощью команд csc.exe или vb.exe.</span><span class="sxs-lookup"><span data-stu-id="8f29a-127">Compile the code at the command line using csc.exe or vb.exe.</span></span> <span data-ttu-id="8f29a-128">Чтобы скомпилировать код в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], поместите его в шаблон проекта консольного приложения.</span><span class="sxs-lookup"><span data-stu-id="8f29a-128">To compile the code in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], put it in a console application project template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f29a-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8f29a-129">See Also</span></span>  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [<span data-ttu-id="8f29a-130">Строки настраиваемых форматов даты и времени</span><span class="sxs-lookup"><span data-stu-id="8f29a-130">Custom Date and Time Format Strings</span></span>](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)

---
title: Базовые операции со строками в .NET
description: Дополнительные сведения о базовых операциях, которые можно выполнять со строками.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
ms.custom: seadec18
ms.openlocfilehash: 05cdf399e104fc9e528c954adb19634a5c136664
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73132914"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="cc126-103">Базовые операции со строками в .NET</span><span class="sxs-lookup"><span data-stu-id="cc126-103">Basic String Operations in .NET</span></span>
<span data-ttu-id="cc126-104">Многие приложения взаимодействуют с пользователями, формируя сообщения, основанные на данных, введенных пользователями.</span><span class="sxs-lookup"><span data-stu-id="cc126-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="cc126-105">Например, веб-узлы зачастую приветствуют вошедших пользователей персональным приветствием, содержащим его имя.</span><span class="sxs-lookup"><span data-stu-id="cc126-105">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="cc126-106">Ряд методов в классах <xref:System.String?displayProperty=nameWithType> и <xref:System.Text.StringBuilder?displayProperty=nameWithType> позволяют динамически создавать настраиваемые строки для отображения в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="cc126-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="cc126-107">С помощью этих методов также можно выполнять базовые операции со строками — например, создание новых строк из байтовых массивов, сравнение значений строк и изменение существующих строк.</span><span class="sxs-lookup"><span data-stu-id="cc126-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc126-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="cc126-108">In This Section</span></span>  
 [<span data-ttu-id="cc126-109">Создание строк</span><span class="sxs-lookup"><span data-stu-id="cc126-109">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="cc126-110">Описывает основные способы комбинирования строк и преобразования объектов в строки.</span><span class="sxs-lookup"><span data-stu-id="cc126-110">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="cc126-111">Сокращение и удаление знаков</span><span class="sxs-lookup"><span data-stu-id="cc126-111">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="cc126-112">Описывает способы сокращения строк и удаления символов из строки.</span><span class="sxs-lookup"><span data-stu-id="cc126-112">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="cc126-113">Заполнение строк</span><span class="sxs-lookup"><span data-stu-id="cc126-113">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="cc126-114">Описывает способы вставки символов или пробелов в строку.</span><span class="sxs-lookup"><span data-stu-id="cc126-114">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="cc126-115">Сравнение строк в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="cc126-115">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="cc126-116">Описывает сравнение содержимого двух или более строк.</span><span class="sxs-lookup"><span data-stu-id="cc126-116">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="cc126-117">Смена регистра</span><span class="sxs-lookup"><span data-stu-id="cc126-117">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="cc126-118">Описывает изменение регистра для символов в строке.</span><span class="sxs-lookup"><span data-stu-id="cc126-118">Describes how to change the case of characters within a string.</span></span>  
  
 <span data-ttu-id="cc126-119">[Using the StringBuilder class](../../../docs/standard/base-types/stringbuilder.md) (Использование класса StringBuilder)</span><span class="sxs-lookup"><span data-stu-id="cc126-119">[Using the StringBuilder Class](../../../docs/standard/base-types/stringbuilder.md)</span></span>  
 <span data-ttu-id="cc126-120">Описывает создание и изменение динамических строковых объектов с помощью класса <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="cc126-120">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="cc126-121">Практическое руководство. Выполнение базовых операций со строками</span><span class="sxs-lookup"><span data-stu-id="cc126-121">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="cc126-122">Демонстрирует использование основных строковых операций.</span><span class="sxs-lookup"><span data-stu-id="cc126-122">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="cc126-123">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="cc126-123">Related Sections</span></span>  
 [<span data-ttu-id="cc126-124">Преобразование типов в .NET</span><span class="sxs-lookup"><span data-stu-id="cc126-124">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="cc126-125">Описывает преобразование одних типов в другие.</span><span class="sxs-lookup"><span data-stu-id="cc126-125">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="cc126-126">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="cc126-126">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="cc126-127">Описывает форматирование строк с использованием описателей формата.</span><span class="sxs-lookup"><span data-stu-id="cc126-127">Describes how to format strings using format specifiers.</span></span>

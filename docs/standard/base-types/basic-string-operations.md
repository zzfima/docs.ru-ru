---
title: "Базовые операции со строками в .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f241b99f97cad081a65fd8654169e444a1b588cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="18262-102">Основные операции со строками в .NET</span><span class="sxs-lookup"><span data-stu-id="18262-102">Basic String Operations in .NET</span></span>
<span data-ttu-id="18262-103">Многие приложения взаимодействуют с пользователями, формируя сообщения, основанные на данных, введенных пользователями.</span><span class="sxs-lookup"><span data-stu-id="18262-103">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="18262-104">Например, веб-узлы зачастую приветствуют вошедших пользователей персональным приветствием, содержащим его имя.</span><span class="sxs-lookup"><span data-stu-id="18262-104">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="18262-105">Несколько методов в <xref:System.String?displayProperty=nameWithType> и <xref:System.Text.StringBuilder?displayProperty=nameWithType> классы позволяют динамически создавать пользовательские строки для отображения в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="18262-105">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="18262-106">С помощью этих методов также можно выполнять базовые операции со строками — например, создание новых строк из байтовых массивов, сравнение значений строк и изменение существующих строк.</span><span class="sxs-lookup"><span data-stu-id="18262-106">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="18262-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="18262-107">In This Section</span></span>  
 [<span data-ttu-id="18262-108">Создание строк</span><span class="sxs-lookup"><span data-stu-id="18262-108">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="18262-109">Описывает основные способы преобразования объектов в строки и объединения строк.</span><span class="sxs-lookup"><span data-stu-id="18262-109">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="18262-110">Сокращение и удаление знаков</span><span class="sxs-lookup"><span data-stu-id="18262-110">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="18262-111">Описывает, как сжатие и удаление знаков в строке.</span><span class="sxs-lookup"><span data-stu-id="18262-111">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="18262-112">Заполнение строк</span><span class="sxs-lookup"><span data-stu-id="18262-112">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="18262-113">Описывает способы вставки символов или пробелов в строку.</span><span class="sxs-lookup"><span data-stu-id="18262-113">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="18262-114">Сравнение строк в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="18262-114">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="18262-115">Описывает, как сравнение содержимого двух или более строк.</span><span class="sxs-lookup"><span data-stu-id="18262-115">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="18262-116">Смена регистра</span><span class="sxs-lookup"><span data-stu-id="18262-116">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="18262-117">Описывает изменение регистра символов в строке.</span><span class="sxs-lookup"><span data-stu-id="18262-117">Describes how to change the case of characters within a string.</span></span>  
  
 <span data-ttu-id="18262-118">[Using the StringBuilder class](../../../docs/standard/base-types/stringbuilder.md) (Использование класса StringBuilder)</span><span class="sxs-lookup"><span data-stu-id="18262-118">[Using the StringBuilder Class](../../../docs/standard/base-types/stringbuilder.md)</span></span>  
 <span data-ttu-id="18262-119">Описывает, как создавать и изменять объекты динамическую строку с <xref:System.Text.StringBuilder> класса.</span><span class="sxs-lookup"><span data-stu-id="18262-119">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="18262-120">Практическое руководство. Выполнение базовых операций со строками</span><span class="sxs-lookup"><span data-stu-id="18262-120">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="18262-121">Демонстрирует использование основные операции со строками.</span><span class="sxs-lookup"><span data-stu-id="18262-121">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="18262-122">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="18262-122">Related Sections</span></span>  
 [<span data-ttu-id="18262-123">Преобразование типов в .NET</span><span class="sxs-lookup"><span data-stu-id="18262-123">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="18262-124">Описывает способ преобразования одного типа в другой тип.</span><span class="sxs-lookup"><span data-stu-id="18262-124">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="18262-125">Типы форматирования</span><span class="sxs-lookup"><span data-stu-id="18262-125">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="18262-126">Описывает форматирование строк с помощью описателей формата.</span><span class="sxs-lookup"><span data-stu-id="18262-126">Describes how to format strings using format specifiers.</span></span>

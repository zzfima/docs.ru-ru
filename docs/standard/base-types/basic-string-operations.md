---
title: "Базовые операции со строками"
description: "Базовые операции со строками"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/26/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 9658098d-de60-4868-ba5b-0c278748a90f
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: b8bdbeccd226c412e725200fcaf81ec568afc5bc
ms.contentlocale: ru-ru
ms.lasthandoff: 03/02/2017

---

# <a name="basic-string-operations"></a><span data-ttu-id="c758c-104">Базовые операции со строками</span><span class="sxs-lookup"><span data-stu-id="c758c-104">Basic string operations</span></span>

<span data-ttu-id="c758c-105">Многие приложения взаимодействуют с пользователями, формируя сообщения, основанные на данных, введенных пользователями.</span><span class="sxs-lookup"><span data-stu-id="c758c-105">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="c758c-106">Например, веб-узлы зачастую приветствуют вошедших пользователей персональным приветствием, содержащим его имя.</span><span class="sxs-lookup"><span data-stu-id="c758c-106">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="c758c-107">Ряд методов в классах [System.String](xref:System.String) и [System.Text.StringBuilder](xref:System.Text.StringBuilder) позволяет динамически создавать настраиваемые строки для их последующего использования в пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="c758c-107">Several methods in the [System.String](xref:System.String) and [System.Text.StringBuilder](xref:System.Text.StringBuilder) classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="c758c-108">С помощью этих методов также можно выполнять базовые операции со строками — например, создание новых строк из байтовых массивов, сравнение значений строк и изменение существующих строк.</span><span class="sxs-lookup"><span data-stu-id="c758c-108">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c758c-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="c758c-109">In This Section</span></span>

<span data-ttu-id="c758c-110">[Создание новых строк](creating-new.md) — основные способы преобразования объектов в строки и комбинирования строк.</span><span class="sxs-lookup"><span data-stu-id="c758c-110">[Creating new strings](creating-new.md) - Describes basic ways to convert objects into strings and to combine strings.</span></span>

<span data-ttu-id="c758c-111">[Сокращение и удаление знаков](trimming.md) — способы сокращения строк и удаления знаков из строки.</span><span class="sxs-lookup"><span data-stu-id="c758c-111">[Trimming and removing characters](trimming.md) - Describes how to trim or remove characters in a string.</span></span> 

<span data-ttu-id="c758c-112">[Заполнение строк](padding.md) — вставка знаков или пробелов в строку.</span><span class="sxs-lookup"><span data-stu-id="c758c-112">[Padding strings](padding.md) - Describes how to insert characters or empty spaces into a string.</span></span>

<span data-ttu-id="c758c-113">[Сравнение строк](comparing.md) — сравнение содержимого двух или более строк.</span><span class="sxs-lookup"><span data-stu-id="c758c-113">[Comparing strings](comparing.md) - Describes how to compare the contents of two or more strings.</span></span>

<span data-ttu-id="c758c-114">[Смена регистра](changing-case.md) — изменение регистра знаков в строке.</span><span class="sxs-lookup"><span data-stu-id="c758c-114">[Changing case](changing-case.md) - Describes how to change the case of characters within a string.</span></span>

<span data-ttu-id="c758c-115">[Использование класса StringBuilder](stringbuilder.md) — создание и изменение динамических строковых объектов с помощью класса [StringBuilder](xref:System.Text.StringBuilder).</span><span class="sxs-lookup"><span data-stu-id="c758c-115">[Using the StringBuilder class](stringbuilder.md) - Describes how to create and modify dynamic string objects with the [StringBuilder](xref:System.Text.StringBuilder) class.</span></span>

<span data-ttu-id="c758c-116">[Практическое руководство. Выполнение базовых операций со строками](basic-manipulations.md) — демонстрация основных операций со строками.</span><span class="sxs-lookup"><span data-stu-id="c758c-116">[How to: Perform basic string manipulations](basic-manipulations.md) - Demonstrates the use of basic string operations.</span></span>

## <a name="related-sections"></a><span data-ttu-id="c758c-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c758c-117">Related Sections</span></span>

<span data-ttu-id="c758c-118">[Преобразование типов](type-conversion.md) — описание порядка преобразования одного типа в другой.</span><span class="sxs-lookup"><span data-stu-id="c758c-118">[Type conversion](type-conversion.md) - Describes how to convert from one type to another.</span></span>

<span data-ttu-id="c758c-119">[Типы форматирования](formatting-types.md) — описание форматирования строк с использованием описателей формата.</span><span class="sxs-lookup"><span data-stu-id="c758c-119">[Formatting types](formatting-types.md) - Describes how to format strings using the string format specifiers.</span></span>




---
title: "Практическое руководство. Добавление данных пользователя в данные рукописного ввода"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ca44d6a2c42219f7aec76f8007010c24c610138
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="367c0-102">Практическое руководство. Добавление данных пользователя в данные рукописного ввода</span><span class="sxs-lookup"><span data-stu-id="367c0-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="367c0-103">Можно добавлять пользовательские данные для рукописного ввода, которая будет сохранена при сохранении рукописный ввод как рукописный ввод сериализованного формата (ISF).</span><span class="sxs-lookup"><span data-stu-id="367c0-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="367c0-104">Можно сохранить пользовательские данные для <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, или <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="367c0-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="367c0-105">Возможность сохранить пользовательские данные в трех объектов дает возможность выбрать лучшее место для сохранения данных.</span><span class="sxs-lookup"><span data-stu-id="367c0-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="367c0-106">Все три класса используют аналогичные методы для хранения и доступа к пользовательским данным.</span><span class="sxs-lookup"><span data-stu-id="367c0-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="367c0-107">Только следующие типы могут сохраняться как пользовательские данные:</span><span class="sxs-lookup"><span data-stu-id="367c0-107">Only the following types can be saved as custom data:</span></span>  
  
-   <xref:System.Boolean>  
  
-   <span data-ttu-id="367c0-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-108"><xref:System.Boolean>[]</span></span>  
  
-   <xref:System.Byte>  
  
-   <span data-ttu-id="367c0-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-109"><xref:System.Byte>[]</span></span>  
  
-   <xref:System.Char>  
  
-   <span data-ttu-id="367c0-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-110"><xref:System.Char>[]</span></span>  
  
-   <xref:System.DateTime>  
  
-   <span data-ttu-id="367c0-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-111"><xref:System.DateTime>[]</span></span>  
  
-   <xref:System.Decimal>  
  
-   <span data-ttu-id="367c0-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-112"><xref:System.Decimal>[]</span></span>  
  
-   <xref:System.Double>  
  
-   <span data-ttu-id="367c0-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-113"><xref:System.Double>[]</span></span>  
  
-   <xref:System.Int16>  
  
-   <span data-ttu-id="367c0-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-114"><xref:System.Int16>[]</span></span>  
  
-   <xref:System.Int32>  
  
-   <span data-ttu-id="367c0-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-115"><xref:System.Int32>[]</span></span>  
  
-   <xref:System.Int64>  
  
-   <span data-ttu-id="367c0-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-116"><xref:System.Int64>[]</span></span>  
  
-   <xref:System.Single>  
  
-   <span data-ttu-id="367c0-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-117"><xref:System.Single>[]</span></span>  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <span data-ttu-id="367c0-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-118"><xref:System.UInt16>[]</span></span>  
  
-   <xref:System.UInt32>  
  
-   <span data-ttu-id="367c0-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-119"><xref:System.UInt32>[]</span></span>  
  
-   <xref:System.UInt64>  
  
-   <span data-ttu-id="367c0-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="367c0-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="367c0-121">Пример</span><span class="sxs-lookup"><span data-stu-id="367c0-121">Example</span></span>  
 <span data-ttu-id="367c0-122">Следующий пример демонстрирует добавление и извлечение пользовательских данных из <xref:System.Windows.Ink.StrokeCollection>.</span><span class="sxs-lookup"><span data-stu-id="367c0-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="367c0-123">В следующем примере создается приложение, которое отображает <xref:System.Windows.Controls.InkCanvas> и две кнопки.</span><span class="sxs-lookup"><span data-stu-id="367c0-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="367c0-124">Кнопка, `switchAuthor`, позволяет использовать два разных авторах два пера.</span><span class="sxs-lookup"><span data-stu-id="367c0-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="367c0-125">Кнопки `changePenColors` изменяет цвет каждого штриха на <xref:System.Windows.Controls.InkCanvas> согласно автору.</span><span class="sxs-lookup"><span data-stu-id="367c0-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="367c0-126">Приложение определяет два <xref:System.Windows.Ink.DrawingAttributes> объектов и добавляет пользовательское свойство для каждого из них, указывающее, какой автор, перетащенной <xref:System.Windows.Ink.Stroke>.</span><span class="sxs-lookup"><span data-stu-id="367c0-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="367c0-127">Когда пользователь щелкает `changePenColors`, приложение изменяет внешний вид штриха согласно значению пользовательского свойства.</span><span class="sxs-lookup"><span data-stu-id="367c0-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]

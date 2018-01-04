---
title: "Двойная буферизация графики"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d83846dcded620b74f7d276fd241a302cce1b60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="using-double-buffering"></a><span data-ttu-id="ebc55-102">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="ebc55-102">Using Double Buffering</span></span>
<span data-ttu-id="ebc55-103">Двойная буферизация графики можно использовать для уменьшения мерцания в приложениях, которые содержат сложных операций рисования.</span><span class="sxs-lookup"><span data-stu-id="ebc55-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="ebc55-104">Платформа .NET Framework содержит встроенную поддержку двойной буферизации или можно управлять и отображения графики вручную.</span><span class="sxs-lookup"><span data-stu-id="ebc55-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebc55-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ebc55-105">In This Section</span></span>  
 [<span data-ttu-id="ebc55-106">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="ebc55-106">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 <span data-ttu-id="ebc55-107">Вводит двойной буферизации поддержки .NET Framework и описание.</span><span class="sxs-lookup"><span data-stu-id="ebc55-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="ebc55-108">Практическое руководство. Уменьшение эффекта мерцания изображения посредством двойной буферизации для форм и элементов управления</span><span class="sxs-lookup"><span data-stu-id="ebc55-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="ebc55-109">Демонстрирует использование поддержки двойной буферизации в .NET Framework по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ebc55-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="ebc55-110">Практическое руководство. Управление буферизацией графики вручную</span><span class="sxs-lookup"><span data-stu-id="ebc55-110">How to: Manually Manage Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="ebc55-111">Показано, как управлять двойной буферизации в приложениях.</span><span class="sxs-lookup"><span data-stu-id="ebc55-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="ebc55-112">Практическое руководство. Прорисовка буферизированной графики вручную</span><span class="sxs-lookup"><span data-stu-id="ebc55-112">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="ebc55-113">Описание способа отображения двойная буферизация графики.</span><span class="sxs-lookup"><span data-stu-id="ebc55-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ebc55-114">Ссылка</span><span class="sxs-lookup"><span data-stu-id="ebc55-114">Reference</span></span>  
 <span data-ttu-id="ebc55-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="ebc55-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="ebc55-116">Метод управления, позволяющий двойной буферизации.</span><span class="sxs-lookup"><span data-stu-id="ebc55-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="ebc55-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="ebc55-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="ebc55-118">Предоставляет методы для создания графических буферов.</span><span class="sxs-lookup"><span data-stu-id="ebc55-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="ebc55-119">Предоставляет доступ к контексту буферизованной графики для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="ebc55-119">Provides access to the buffered graphics context for a application domain.</span></span>

---
title: Двойная буферизация графики
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: ac6c9b7f2cc1fea86a75eaaf4a2dde1ea60e4f40
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716292"
---
# <a name="using-double-buffering"></a><span data-ttu-id="b906f-102">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="b906f-102">Using Double Buffering</span></span>
<span data-ttu-id="b906f-103">Двойная буферизация графики можно использовать для уменьшения эффекта дрожания изображения в приложениях, которые содержат сложных операций рисования.</span><span class="sxs-lookup"><span data-stu-id="b906f-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="b906f-104">.NET Framework содержит встроенную поддержку двойной буферизации или вы можете управлять и отображения графики вручную.</span><span class="sxs-lookup"><span data-stu-id="b906f-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b906f-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b906f-105">In This Section</span></span>  
 [<span data-ttu-id="b906f-106">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="b906f-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="b906f-107">Появилась двойной буферизации поддержка .NET Framework и описание.</span><span class="sxs-lookup"><span data-stu-id="b906f-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="b906f-108">Практическое руководство. Уменьшить мерцания изображения посредством двойной буферизации для форм и элементов управления</span><span class="sxs-lookup"><span data-stu-id="b906f-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="b906f-109">Демонстрирует использование поддержки двойной буферизации в .NET Framework по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b906f-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="b906f-110">Практическое руководство. Управление буферизацией графики</span><span class="sxs-lookup"><span data-stu-id="b906f-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="b906f-111">Описывает процессы управления двойной буферизации в приложениях.</span><span class="sxs-lookup"><span data-stu-id="b906f-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="b906f-112">Практическое руководство. Визуализация буферизированной графики вручную</span><span class="sxs-lookup"><span data-stu-id="b906f-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="b906f-113">Показана Подготовка к просмотру двойная буферизация графики.</span><span class="sxs-lookup"><span data-stu-id="b906f-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b906f-114">Ссылка</span><span class="sxs-lookup"><span data-stu-id="b906f-114">Reference</span></span>  
 <span data-ttu-id="b906f-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="b906f-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="b906f-116">Метод Control, который позволяет двойной буферизации.</span><span class="sxs-lookup"><span data-stu-id="b906f-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="b906f-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="b906f-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="b906f-118">Предоставляет методы для создания графических буферов.</span><span class="sxs-lookup"><span data-stu-id="b906f-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="b906f-119">Предоставляет доступ к контексту буферизованной графики для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="b906f-119">Provides access to the buffered graphics context for a application domain.</span></span>

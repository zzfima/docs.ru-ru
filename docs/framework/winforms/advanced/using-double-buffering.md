---
title: Двойная буферизация графики
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2019
ms.locfileid: "67169910"
---
# <a name="using-double-buffering"></a><span data-ttu-id="deb99-102">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="deb99-102">Using Double Buffering</span></span>
<span data-ttu-id="deb99-103">Двойная буферизация графики можно использовать для уменьшения эффекта дрожания изображения в приложениях, которые содержат сложных операций рисования.</span><span class="sxs-lookup"><span data-stu-id="deb99-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="deb99-104">.NET Framework содержит встроенную поддержку двойной буферизации или вы можете управлять и отображения графики вручную.</span><span class="sxs-lookup"><span data-stu-id="deb99-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="deb99-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="deb99-105">In This Section</span></span>  
 [<span data-ttu-id="deb99-106">Двойная буферизация графики</span><span class="sxs-lookup"><span data-stu-id="deb99-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="deb99-107">Появилась двойной буферизации поддержка .NET Framework и описание.</span><span class="sxs-lookup"><span data-stu-id="deb99-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="deb99-108">Практическое руководство. Уменьшить мерцания изображения посредством двойной буферизации для форм и элементов управления</span><span class="sxs-lookup"><span data-stu-id="deb99-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="deb99-109">Демонстрирует использование поддержки двойной буферизации в .NET Framework по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="deb99-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="deb99-110">Практическое руководство. Управление буферизацией графики</span><span class="sxs-lookup"><span data-stu-id="deb99-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="deb99-111">Описывает процессы управления двойной буферизации в приложениях.</span><span class="sxs-lookup"><span data-stu-id="deb99-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="deb99-112">Практическое руководство. Визуализация буферизированной графики вручную</span><span class="sxs-lookup"><span data-stu-id="deb99-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="deb99-113">Показана Подготовка к просмотру двойная буферизация графики.</span><span class="sxs-lookup"><span data-stu-id="deb99-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="deb99-114">Ссылка</span><span class="sxs-lookup"><span data-stu-id="deb99-114">Reference</span></span>  
 <span data-ttu-id="deb99-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Метод Control, который позволяет двойной буферизации.</span><span class="sxs-lookup"><span data-stu-id="deb99-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="deb99-116"><xref:System.Drawing.BufferedGraphicsContext> Предоставляет методы для создания графических буферов.</span><span class="sxs-lookup"><span data-stu-id="deb99-116"><xref:System.Drawing.BufferedGraphicsContext> Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="deb99-117">Предоставляет доступ к контексту буферизованной графики для домена приложения.</span><span class="sxs-lookup"><span data-stu-id="deb99-117">Provides access to the buffered graphics context for a application domain.</span></span>

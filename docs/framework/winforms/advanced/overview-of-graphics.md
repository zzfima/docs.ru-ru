---
title: Обзор графических возможностей
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: f0e2fd9dcf31e5fdce16b5a3b6fd21eab6eab66a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505318"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="0e79d-102">Обзор графических возможностей</span><span class="sxs-lookup"><span data-stu-id="0e79d-102">Overview of Graphics</span></span>
<span data-ttu-id="0e79d-103">GDI + — прикладной программный интерфейс (API), формирует подсистему операционной системы Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="0e79d-103">GDI+ is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> <span data-ttu-id="0e79d-104">GDI + отвечает за отображение информации на экранах и принтерах.</span><span class="sxs-lookup"><span data-stu-id="0e79d-104">GDI+ is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="0e79d-105">Как предполагает имя, GDI + является преемником GDI, интерфейса графических устройств, в состав более ранних версиях Windows.</span><span class="sxs-lookup"><span data-stu-id="0e79d-105">As its name suggests, GDI+ is the successor to GDI, the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="0e79d-106">Интерфейс управляемых классов</span><span class="sxs-lookup"><span data-stu-id="0e79d-106">Managed Class Interface</span></span>  
 <span data-ttu-id="0e79d-107">GDI + API предоставляется через набор классов, развертываемых как управляемый код.</span><span class="sxs-lookup"><span data-stu-id="0e79d-107">The GDI+ API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="0e79d-108">Этот набор классов называется *интерфейс управляемых классов* в GDI +.</span><span class="sxs-lookup"><span data-stu-id="0e79d-108">This set of classes is called the *managed class interface* to GDI+.</span></span> <span data-ttu-id="0e79d-109">Интерфейс управляемых классов состоит из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="0e79d-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="0e79d-110">С помощью интерфейса графических устройств, таких как GDI + могут отображать данные на экран или принтер без необходимости думать о деталях конкретного устройства отображения.</span><span class="sxs-lookup"><span data-stu-id="0e79d-110">With a Graphics Device Interface, such as GDI+, you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="0e79d-111">Программист вызывает методы, предоставляемые классами GDI +.</span><span class="sxs-lookup"><span data-stu-id="0e79d-111">The programmer makes calls to methods provided by GDI+ classes.</span></span> <span data-ttu-id="0e79d-112">Эти методы, в свою очередь, осуществляют вызовы драйверов определенных устройств.</span><span class="sxs-lookup"><span data-stu-id="0e79d-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> <span data-ttu-id="0e79d-113">GDI + изолирует приложение от графического оборудования.</span><span class="sxs-lookup"><span data-stu-id="0e79d-113">GDI+ insulates the application from the graphics hardware.</span></span> <span data-ttu-id="0e79d-114">Это такая изоляция дает программистам возможность создавать аппаратно независимые приложения.</span><span class="sxs-lookup"><span data-stu-id="0e79d-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e79d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0e79d-115">See also</span></span>

- [<span data-ttu-id="0e79d-116">Общие сведения о графике</span><span class="sxs-lookup"><span data-stu-id="0e79d-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)

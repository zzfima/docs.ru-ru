---
title: Обзор графических возможностей
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: 8d8e1ab286d4e5723f5ca6bca0b6eeff53ac1d43
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57711348"
---
# <a name="overview-of-graphics"></a><span data-ttu-id="4ebc1-102">Обзор графических возможностей</span><span class="sxs-lookup"><span data-stu-id="4ebc1-102">Overview of Graphics</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="4ebc1-103">— прикладной программный интерфейс (API), формирует подсистему операционной системы Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="4ebc1-103">is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="4ebc1-104">отвечает за отображение информации на экранах и принтерах.</span><span class="sxs-lookup"><span data-stu-id="4ebc1-104">is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="4ebc1-105">Как видно из имени, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] является последователем [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], интерфейса графических устройств, входившего в состав более ранних версий Windows.</span><span class="sxs-lookup"><span data-stu-id="4ebc1-105">As its name suggests, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is the successor to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="4ebc1-106">Интерфейс управляемых классов</span><span class="sxs-lookup"><span data-stu-id="4ebc1-106">Managed Class Interface</span></span>  
 <span data-ttu-id="4ebc1-107">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API предоставляется через набор классов, развертываемых как управляемый код.</span><span class="sxs-lookup"><span data-stu-id="4ebc1-107">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="4ebc1-108">Этот набор классов называется *интерфейс управляемых классов* для [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ebc1-108">This set of classes is called the *managed class interface* to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="4ebc1-109">Интерфейс управляемых классов состоит из следующих пространств имен.</span><span class="sxs-lookup"><span data-stu-id="4ebc1-109">The following namespaces make up the managed class interface:</span></span>  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="4ebc1-110">С помощью интерфейса графических устройств таких как [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], можно отображать данные на экран или принтер без необходимости думать о деталях конкретного устройства отображения.</span><span class="sxs-lookup"><span data-stu-id="4ebc1-110">With a Graphics Device Interface, such as [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="4ebc1-111">Программист вызывает методы, предоставляемые классами [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4ebc1-111">The programmer makes calls to methods provided by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span> <span data-ttu-id="4ebc1-112">Эти методы, в свою очередь, осуществляют вызовы драйверов определенных устройств.</span><span class="sxs-lookup"><span data-stu-id="4ebc1-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <span data-ttu-id="4ebc1-113">изолирует приложение от графического оборудования.</span><span class="sxs-lookup"><span data-stu-id="4ebc1-113">insulates the application from the graphics hardware.</span></span> <span data-ttu-id="4ebc1-114">Это такая изоляция дает программистам возможность создавать аппаратно независимые приложения.</span><span class="sxs-lookup"><span data-stu-id="4ebc1-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebc1-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4ebc1-115">See also</span></span>
- [<span data-ttu-id="4ebc1-116">Общие сведения о графике</span><span class="sxs-lookup"><span data-stu-id="4ebc1-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)

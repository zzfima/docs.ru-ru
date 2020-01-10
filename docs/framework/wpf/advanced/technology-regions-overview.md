---
title: Общие сведения об областях применения технологий
ms.date: 03/30/2017
helpviewer_keywords:
- window regions [WPF]
- Win32 code [WPF], WPF interoperation
- Win32 code [WPF], airspace
- airspace [WPF]
- interoperability [WPF], airspace
- Win32 code [WPF], window regions
ms.assetid: b7cc350f-b9e2-48b1-be14-60f3d853222e
ms.openlocfilehash: 0b6ad222737f992da3074770fb5a2bff17860c00
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740289"
---
# <a name="technology-regions-overview"></a>Общие сведения об областях применения технологий
Если в приложении используются несколько технологий представления, такие как WPF, Win32 или DirectX, то они должны совместно использовать области отрисовки в общем окне верхнего уровня. В этом разделе описываются проблемы, которые могут повлиять на представление и выходные данные приложения взаимодействия с WPF.  
  
## <a name="regions"></a>Области  
 В окне верхнего уровня можно представить, что каждый HWND, который представляет собой одну из технологий приложения взаимодействия, имеет собственную область (также называемую "свободное пространство"). Каждый пиксель в окне принадлежит только одному дескриптору HWND, который определяет область этого HWND. (Строго говоря, существует более одной области [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], если имеется более одного HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], но для целей этого обсуждения можно предположить, что есть только один). Область подразумевает, что все слои или другие окна, которые пытаются отобразиться поверх этого пикселя во время существования приложения, должны быть частью одной и той же технологии уровня отрисовки. Попытка прорисовки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] пикселей по Win32 приводит к нежелательным результатам и не позволяет максимально использовать их через API взаимодействия.  
  
### <a name="region-examples"></a>Примеры областей  
 На следующем рисунке показано приложение, которое смешивается с Win32, DirectX и [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Каждая технология использует отдельный, неперекрывающийся набор пикселей, и проблемы с областями отсутствуют.  
  
 ![Пример приложения, которое смешивает Win32, DirectX и WPF.](./media/technology-regions-overview/win32-directx-windows-presentation-foundation-application.png)  
  
 Предположим, что это приложение использует положение указателя мыши для создания анимации, которая пытается выполнить отрисовку поверх любой из этих трех областей. Независимо от того, какая технология отвечает за анимацию, эта технология нарушила бы область двух других. На рисунке показана попытка отрисовать круг WPF поверх области Win32.  
  
 ![Попытка отрисовки окружности WPF в области Win32.](./media/technology-regions-overview/render-windows-presentation-foundation-circle-over-win32-region.png)  
  
 Другое нарушение — это попытка использовать прозрачность/альфа-смешение между различными технологиями.  На следующем рисунке [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поле нарушает области Win32 и DirectX. Поскольку Пиксели в этом [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поле являются полупрозрачными, они должны быть совместно связаны как с DirectX, так и с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], что невозможно.  Так что это еще одно нарушение, и его нельзя построить.  
  
 ![Схема, показывающая, что окно WPF нарушает регионы Win32 и DirectX.](./media/technology-regions-overview/windows-foundation-presentation-box-violate-win32-directx-region.png)  
  
 В предыдущих трех примерах использовались прямоугольные области, но возможны разные формы.  Например, в области может быть отверстие. На следующем рисунке показан регион Win32 с прямоугольной отверстием. это размер областей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и DirectX.  
  
 ![Диаграмма, на которой показан регион Win32 с прямоугольным отверстием.](./media/technology-regions-overview/win32-region-rectangular-hole.png)  
  
 Регионы также могут быть полностью непрямоугольными или любой фигурой, дескрибабле в Win32 ХРГН (Region).  
  
 ![Схема, на которой показана непрямоугольная область.](./media/technology-regions-overview/nonrectangular-win32-region.png)  
  
## <a name="transparency-and-top-level-windows"></a>Прозрачность и окна верхнего уровня  
 Диспетчер окон в Windows действительно обрабатывает только HWND Win32. Таким образом, каждый [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> является HWND. <xref:System.Windows.Window> HWND должен соответствовать общим правилам для любого HWND. В этом HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] код может выполнять любые общие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ные API-интерфейсы. Но для взаимодействия с другими HWND на рабочем столе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] должны соблюдать правила обработки и отрисовки Win32.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает непрямоугольные окна с помощью API-интерфейсов Win32 — HRGN для непрямоугольных окон и многоуровневых окон для альфа-канала на пиксель.  
  
 Постоянные альфа- и цветовые ключи не поддерживаются.  Возможности многоуровневого окна Win32 зависят от платформы.  
  
 Многослойные окна позволяют сделать все окно прозрачным (полупрозрачным), указав альфа-значение, которое применяется к каждому пикселю в окне.  (Win32 фактически поддерживает альфа-канал, но это очень трудно использовать в практических программах, так как в этом режиме необходимо нарисовать любой дочерний HWND самостоятельно, включая диалоговые окна и раскрывающиеся списки).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] поддерживает HRGN; Однако для этой функции нет управляемых API. Можно использовать вызов неуправляемого кода и <xref:System.Windows.Interop.HwndSource> для вызова соответствующих API-интерфейсов Win32. Дополнительную информацию см. в разделе [Вызов встроенных функций из управляемого кода](/cpp/dotnet/calling-native-functions-from-managed-code).  
  
 Многослойные окна [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют разные функциональные возможности в различных операционных системах. Это связано с тем, что [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] использует DirectX для визуализации, а многослойные окна — в первую очередь для отрисовки GDI, а не для отрисовки DirectX.  
  
- WPF поддерживает многоуровневые окна с аппаратным ускорением.  
  
- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не поддерживает цветовые ключи прозрачности, так как [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не может гарантировать отрисовку необходимого цвета, особенно при использовании аппаратного ускорения.  
  
## <a name="see-also"></a>См. также:

- [Взаимодействие WPF и Win32](wpf-and-win32-interoperation.md)
- [Пошаговое руководство. Размещение часов WPF в Win32](walkthrough-hosting-a-wpf-clock-in-win32.md)
- [Размещение содержимого Win32 в WPF](hosting-win32-content-in-wpf.md)

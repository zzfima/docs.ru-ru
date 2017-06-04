---
title: "Using Manipulations and Inertia in an XNA Application | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# Using Manipulations and Inertia in an XNA Application
В этой статье описывается, как можно использовать  обработку манипуляций и инерции в приложении Microsoft XNA для управления движением элементов игры.  Прежде чем приступить к чтению данной статьи, следует ознакомиться со статьей [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md); кроме того, потребуется знакомство с основными концепциями программирования XNA.  
  
 Для выполнения задач, описанных в этой статье, ваш проект XNA должен ссылаться на сборку <xref:System.Windows.Input.Manipulations>, и на компьютере должна быть установлена студия игр [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) \([загрузки](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)\), чтобы проект мог ссылаться на сборки XNA.  
  
## Обзор функциональных возможностей  
 В этой статье показано, как создать пользовательский класс, представляющий элемент игры, который использует обработку манипуляций и инерции.  Этот класс позволяет управлять элементом игры на экране, перетаскивая его с помощью мыши, а затем освобождая его.  После освобождения обработка инерции сохраняет движение элемента, как будто он постепенно замедляется.  Перемещение как линейное, так и угловое.  
  
 ![Приложение простых манипуляций и инерции](../../../docs/framework/common-client-technologies/media/ndp-gamexna.png "NDP\_GameXna")  
  
 Кроме того, создается пользовательская коллекция, управляющая несколькими элементами игры.  Это упрощает обработку, требуемую классом Game XNA.  
  
 [Creating the GamePiece Class](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [Creating the GamePieceCollection Class](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [Creating the Game1 Class](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [Full Code Listings](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## См. также  
 <xref:System.Windows.Input.Manipulations>   
 [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
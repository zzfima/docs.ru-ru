---
title: "Использование графических контейнеров | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], графические контейнеры"
  - "графические контейнеры"
  - "графика, использование контейнеров"
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Использование графических контейнеров
У объекта <xref:System.Drawing.Graphics> имеются методы для отображения векторной и растровой графики, а также текста, например методы <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A> и <xref:System.Drawing.Graphics.DrawString%2A>.  Объект <xref:System.Drawing.Graphics> содержит также некоторые свойства, влияющие на качество и ориентацию отображаемых объектов.  Например, свойство "режим сглаживания" определяет, следует ли применять сглаживание к прямым и кривым линиям, а свойство "объемное преобразование" влияет на расположение и поворот рисуемых объектов.  
  
 Объект <xref:System.Drawing.Graphics> привязывается к конкретному устройству отображения.  При использовании объекта <xref:System.Drawing.Graphics> для рисования в окне этот объект <xref:System.Drawing.Graphics> также привязывается к рассматриваемому окну.  
  
 Объект <xref:System.Drawing.Graphics> можно рассматривать как контейнер, потому что он хранит набор свойств, влияющих на отображение, и привязывается к конкретному устройству.  Можно создать вторичный контейнер внутри существующего объекта <xref:System.Drawing.Graphics>, используя вызов метода <xref:System.Drawing.Graphics.BeginContainer%2A> объекта <xref:System.Drawing.Graphics>.  
  
## В этом подразделе  
 [Управление состоянием объекта Graphics](../../../../docs/framework/winforms/advanced/managing-the-state-of-a-graphics-object.md)  
 Управление параметрами качества, областью обрезки и преобразованиями объекта <xref:System.Drawing.Graphics>.  
  
 [Использование вложенных графических контейнеров](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)  
 Использование контейнеров для управления состоянием объекта <xref:System.Drawing.Graphics>.
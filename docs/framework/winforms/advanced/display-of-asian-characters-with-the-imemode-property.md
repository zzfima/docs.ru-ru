---
title: "Display of Asian Characters with the ImeMode Property | Microsoft Docs"
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
  - "Asian languages, displaying with ImeMode"
  - "Chinese characters, displaying with ImeMode"
  - "IME mode"
  - "Japanese characters, displaying with ImeMode"
  - "international applications [Windows Forms], character display"
  - "international characters"
  - "Korean characters"
  - "Asian languages"
  - "Input Method Editor (IME), mode"
  - "localization [Windows Forms], character sets"
  - "IMEMode property"
  - "globalization [Windows Forms], character sets"
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Display of Asian Characters with the ImeMode Property
Свойство <xref:System.Windows.Forms.Control.ImeMode%2A> используется формами и элементами управления для принудительного перехода к определенному режиму редактора метода ввода \(IME\).  Редактор метода ввода — это необходимый компонент для ввода текста на китайском, японском и корейском языках, так как количество знаков в этих системах письма превышает возможности кодирования обычной клавиатуры.  Например, может потребоваться разрешить для определенного текстового поля только знаки ASCII.  В таком случае можно установить для свойства <xref:System.Windows.Forms.Control.ImeMode%2A> значение <xref:System.Windows.Forms.ImeMode>, после чего пользователи смогут вводить в данное текстовое поле только знаки ASCII.  По умолчанию значение свойства <xref:System.Windows.Forms.Control.ImeMode%2A> равно <xref:System.Windows.Forms.ImeMode>, поэтому, если установить это свойство для формы, все элементы управления в форме унаследуют это значение.  Дополнительные сведения см. в разделах [Свойство Control.ImeMode](frlrfSystemWindowsFormsControlClassImeModeTopic) и [Перечисление ImeMode](frlrfSystemWindowsFormsImeModeClassTopic).  
  
## См. также  
 [Globalizing Windows Forms](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
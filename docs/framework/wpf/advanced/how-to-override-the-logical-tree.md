---
title: "Как переопределить логическое дерево | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "логическое дерево, переопределение"
  - "Переопределение логического дерева"
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Как переопределить логическое дерево
Хотя это и не является необходимым в большинстве случаев, авторы дополнительных элементов управления могут переопределить [логическое дерево](GTMT).  
  
## Пример  
 В этом примере описано, как создать подкласс <xref:System.Windows.Controls.StackPanel>, чтобы переопределить логическое дерево, в данном случае — изменяя поведение панели, которая будет отображать только один дочерний элемент.  Это поведение не является необходимым на практике, но представлено здесь, чтобы показать скрипт для переопределения стандартного логического дерева элемента.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Дополнительные сведения о логическом дереве см. в разделе [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).
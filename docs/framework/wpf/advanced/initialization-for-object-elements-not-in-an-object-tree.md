---
title: "Инициализация для элементов типа Object вне дерева объектов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- logical tree [WPF]
- visual tree [WPF]
- elements [WPF], initializing
- initializing elements [WPF]
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a2a4dd10b664dc349b0c413d7abac03280f8fb8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="initialization-for-object-elements-not-in-an-object-tree"></a>Инициализация для элементов типа Object вне дерева объектов
За некоторые аспекты инициализации [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] отвечают процессы, которые обычно предполагают, что элемент подключен либо к логическому, либо к визуальному дереву. В этом разделе описываются действия, необходимые для инициализации элемента, который не подключен ни к одному из деревьев.  
  
 
  
## <a name="elements-and-the-logical-tree"></a>Элементы и логическое дерево  
 При создании экземпляра класса [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] в коде следует иметь в виду, что несколько аспектов инициализации объекта для класса [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] преднамеренно не являются частью кода, выполняющегося при вызове конструктора класса. Большая часть визуального представления элемента управления, особенно для класса элемента управления, не определяется конструктором. Вместо этого визуальное представление определяется шаблоном элемента управления. Шаблон может быть получен из различных источников, но наиболее часто он берется из стилей темы. Шаблоны фактически выполняют позднее связывание. Необходимый шаблон не присоединяется к элементу управления до тех пор, пока элемент управления не будет подготовлен для макета. А элемент управления не готов для макета до тех пор, пока он не будет присоединен к логическому дереву, которое подключается к отрисовываемой поверхности в корневом элементе. Именно элемент корневого уровня инициирует отрисовку всех дочерних элементов, как определено в логическом дереве.  
  
 Визуальное дерево также участвует в этом процессе. Элементы, которые являются частью визуального дерева посредством шаблонов, также полностью не создаются до тех пор, пока не произойдет подключение.  
  
 Последствием этого является то, что для определенных операций, зависящих от завершенных визуальных характеристик элемента, требуется выполнение дополнительных действий. Примером является попытка получить визуальные характеристики класса, который был создан, но еще не присоединен к дереву. Для экземпляра Если вы хотите вызвать <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A> на <xref:System.Windows.Media.Imaging.RenderTargetBitmap> и визуальный элемент не подключен к дереву элемента не визуально завершена, пока не будут выполнены дополнительные шаги инициализации.  
  
### <a name="using-begininit-and-endinit-to-initialize-the-element"></a>Использование BeginInit и EndInit для инициализации элемента  
 Различные классы [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализовать <xref:System.ComponentModel.ISupportInitialize> интерфейса. Вы используете <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> и <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> методы интерфейса для обозначения области кода, содержащей действия для инициализации (такие как установка значений свойств, влияющих на отрисовку). После <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> вызывается в последовательности, система макета может обработать элемент и начать поиск неявный стиль.  
  
 Если элемент установке свойств на <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> производного класса, то можно вызвать версии класса <xref:System.Windows.FrameworkElement.BeginInit%2A> и <xref:System.Windows.FrameworkElement.EndInit%2A> вместо приведения к <xref:System.ComponentModel.ISupportInitialize>.  
  
### <a name="sample-code"></a>Пример кода  
 Ниже приведен пример кода для консольного приложения, использующего отрисовки [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] и <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=nameWithType> свободного [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] показано правильное размещение файла <xref:System.Windows.FrameworkElement.BeginInit%2A> и <xref:System.Windows.FrameworkElement.EndInit%2A> вокруг других [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] вызовы Настройте свойства, которые влияют на отрисовку.  
  
 В этом примере иллюстрируется только основная функция. Функции `Rasterize` и `Save` (не показаны) являются служебными функциями, которые отвечают за обработку изображения и ввод-вывод.  
  
 [!code-csharp[InitializeElements#Main](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## <a name="see-also"></a>См. также  
 [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)  
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)  
 [Общие сведения о языке XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)

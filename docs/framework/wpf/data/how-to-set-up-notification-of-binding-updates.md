---
title: "Практическое руководство. Настройка уведомлений обновлений привязок"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a07337e99e985bfbc0a5dbc5f2d231ee36cf1422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-up-notification-of-binding-updates"></a>Практическое руководство. Настройка уведомлений обновлений привязок
В этом примере показано, как настроить уведомления об обновлении свойства цели привязки (целевой) или источника привязки (источник) для привязки.  
  
## <a name="example"></a>Пример  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]вызывает событие обновления данных каждый раз при обновлении источника или цели привязки. Внутри системы это событие используется для информирования [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], что он должен быть обновлен, поскольку связанные данные были изменены. Обратите внимание, что для работы этих событий, а также для односторонняя или двусторонняя привязка для правильной работы необходимо реализовать класс данных с помощью <xref:System.ComponentModel.INotifyPropertyChanged> интерфейса. Дополнительные сведения см. в разделе [Реализация уведомления об изменении свойств](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md).  
  
 Задать <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> или <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> (или оба) для `true` в привязке. Обработчик, который предоставляется для ожидания данного события, должен быть подключен непосредственно к элементу, где вы хотите получать сведения об изменениях, или к контексту общих данных, чтобы получить информацию о любом изменении в контексте.  
  
 Ниже приведен пример, в котором показано, как настроить уведомления при обновлении свойства цели привязки.  
  
 [!code-xaml[DirectionalBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 Затем можно назначить обработчик, основанный на делегате EventHandler\<T>, в этом примере *OnTargetUpdated*, для обработки события:  
  
 [!code-csharp[DirectionalBinding#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 Параметры события можно использовать для задания сведений об измененном свойстве (например, типа или конкретного элемента, если один обработчик подключен к нескольким элементам), что может оказаться полезным в том случае, если существует несколько связанных свойств для одного элемента.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)

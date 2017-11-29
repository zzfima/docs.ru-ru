---
title: "Практическое руководство. Создание привязки к методу"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0c276e9da3eaaf786038a117532848364b03e9b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-method"></a>Практическое руководство. Создание привязки к методу
В следующем примере показано, как выполнить привязку к методу с помощью <xref:System.Windows.Data.ObjectDataProvider>.  
  
## <a name="example"></a>Пример  
 В этом примере `TemperatureScale` — это класс, у которого есть метод `ConvertTemp`, принимающий два параметра (один из `double` и один из `enum` типа `TempType)`) и преобразующий данное значение из одной температурной шкалы в другую. В следующем примере <xref:System.Windows.Data.ObjectDataProvider> используется для создания `TemperatureScale` объекта. Метод `ConvertTemp` вызывается с двумя заданными параметрами.  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Теперь, когда метод доступен как ресурс, вы можете привязывать к его результатам. В следующем примере <xref:System.Windows.Controls.TextBox.Text%2A> свойство <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> из <xref:System.Windows.Controls.ComboBox> связаны два параметра метода. Таким образом, пользователи могут указывать исходную и целевую температурную шкалу. Обратите внимание, что <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> равно `true` , так как выполняется привязка к <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> свойство <xref:System.Windows.Data.ObjectDataProvider> экземпляра, а не свойствами объекта, оболочкой для которого <xref:System.Windows.Data.ObjectDataProvider> ( `TemperatureScale` объекта).  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> Последней <xref:System.Windows.Controls.Label> обновления, когда пользователь изменяет содержимое <xref:System.Windows.Controls.TextBox> или выбор <xref:System.Windows.Controls.ComboBox>.  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Преобразователь `DoubleToString` принимает значение типа double и преобразует его в строку в <xref:System.Windows.Data.IValueConverter.Convert%2A> направлении (от источника привязки в целевой объект привязки, который является <xref:System.Windows.Controls.TextBox.Text%2A> свойства) и преобразует `string` для `double` в <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> направление.  
  
 `InvalidationCharacterRule` — <xref:System.Windows.Controls.ValidationRule> , Когда проверяется наличие недопустимых символов. Шаблон по умолчанию ошибки красной границы вокруг <xref:System.Windows.Controls.TextBox>, появляется для уведомления пользователей, если входное значение не является значением типа double.  
  
## <a name="see-also"></a>См. также  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Привязка к перечислению](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)

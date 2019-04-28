---
title: Практическое руководство. Настройка поведения (службы данных WCF) привязки данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
ms.openlocfilehash: f55c9790b8300a1a3f26e031a17a0982638b562b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765522"
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Практическое руководство. Настройка поведения (службы данных WCF) привязки данных
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют добавлять специализированную логику, которая вызывается коллекцией <xref:System.Data.Services.Client.DataServiceCollection%601> при добавлении или удалении объекта из коллекции привязок или при изменении значения свойства. Специализированная логика представляется методами, называемое <xref:System.Func%602> делегатов, возвращающих значение `false` при поведение по умолчанию по-прежнему будет выполняться при завершении пользовательского метода и `true` при дальнейшей обработки из событие должно быть остановлено.  
  
 Примеры в этом разделе добавляют специализированные методы для обоих параметров `entityChanged` и `entityCollectionChanged` коллекции <xref:System.Data.Services.Client.DataServiceCollection%601>. Примеры в этом разделе используют образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются при завершении [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующая страница с выделенным кодом для файла XAML создает коллекцию <xref:System.Data.Services.Client.DataServiceCollection%601> со специализированными методами, которые вызываются при внесении изменений в данные, привязанные к коллекции. При возникновении события <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged> добавленный метод предотвращает удаление из службы данных элемента, удаленного из коллекции привязок. При возникновении события <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged> значение `ShipDate` проверяется, чтобы изменения не проводились над заказами, которые уже были доставлены.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Пример  
 Следующий код XAML определяет окно для предыдущего примера.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)

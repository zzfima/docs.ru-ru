---
title: Практическое руководство. Настройка поведения привязки данных (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
ms.openlocfilehash: c878096cba7d31e0b48727213ee1bb8239b8f690
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790760"
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Практическое руководство. Настройка поведения привязки данных (WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют добавлять специализированную логику, которая вызывается коллекцией <xref:System.Data.Services.Client.DataServiceCollection%601> при добавлении или удалении объекта из коллекции привязок или при изменении значения свойства. Эта пользовательская логика предоставляется в виде методов, <xref:System.Func%602> на которые ссылаются как делегаты, `false` которые возвращают значение, если поведение по умолчанию должно быть выполнено при завершении пользовательского метода и `true` при последующей обработке событие должно быть остановлено.  
  
 Примеры в этом разделе добавляют специализированные методы для обоих параметров `entityChanged` и `entityCollectionChanged` коллекции <xref:System.Data.Services.Client.DataServiceCollection%601>. Примеры в этом разделе используют образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Пример  
 Следующая страница с выделенным кодом для файла XAML создает коллекцию <xref:System.Data.Services.Client.DataServiceCollection%601> со специализированными методами, которые вызываются при внесении изменений в данные, привязанные к коллекции. При возникновении события <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged> добавленный метод предотвращает удаление из службы данных элемента, удаленного из коллекции привязок. При возникновении события <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged> значение `ShipDate` проверяется, чтобы изменения не проводились над заказами, которые уже были доставлены.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Пример  
 Следующий код XAML определяет окно для предыдущего примера.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)

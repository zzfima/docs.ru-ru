---
title: Как выполнить Настройка каналов с использованием поставщика Entity Framework (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: fd16272e-36f2-415e-850e-8a81f2b17525
ms.openlocfilehash: 51e85fa108775806d2c92935868d7ed68534818f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587977"
---
# <a name="how-to-customize-feeds-with-the-entity-framework-provider-wcf-data-services"></a>Как выполнить Настройка каналов с использованием поставщика Entity Framework (WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют настроить сериализацию Atom в ответе службы данных так, чтобы свойства сущности сопоставлялись с неиспользуемыми элементами, определенными в протоколе AtomPub. Этот раздел показывает, как настроить атрибуты сопоставления типов сущностей в модели данных, определенных в файле EDMX, с помощью поставщика Entity Framework. Дополнительные сведения см. в разделе [настройки веб-канала](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 В этом разделе мы вручную изменим сформированный программой файл EDMX, содержащий модель данных. Поскольку расширения модели данных не поддерживаются конструктором сущностей, необходимо вручную модифицировать этот файл. Дополнительные сведения о EDMX-файл, создаваемый средства модели EDM, см. в разделе [Обзор файла .edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4). Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются при завершении [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="to-manually-modify-the-northwindedmx-file-to-add-feed-customization-attributes"></a>Изменение файла Northwind.edmx вручную для добавления атрибутов настройки каналов  
  
1.  В **обозревателе решений**, щелкните правой кнопкой мыши `Northwind.edmx` файла и нажмите кнопку **открыть с помощью**.  
  
2.  В **открыть с помощью — Northwind.edmx** выберите **редактор XML**, а затем нажмите кнопку **ОК**.  
  
3.  Найдите элемент `ConceptualModels` и замените имеющийся тип сущности `Customers` на элемент, содержащий атрибуты сопоставления для настройки канала.  
  
     [!code-xml[Astoria Custom Feeds#EdmFeedCustomers](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/northwind.csdl#edmfeedcustomers)]  
  
4.  Сохраните изменения и закройте файл Northwind.edmx.  
  
5.  (Необязательно) Щелкните файл Northwind.edmx правой кнопкой мыши и выберите **пользовательское средство**.  
  
     При этом будет повторно сформирован файл уровня объектов, который может потребоваться.  
  
6.  Перекомпилируйте проект.  
  
## <a name="example"></a>Пример  
 Предыдущий пример возвращает следующий результат для URI `http://myservice/``Northwind.svc/Customers('ALFKI')`.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/edmfeedresult.xml#edmfeedresult)]  
  
## <a name="see-also"></a>См. также
- [Поставщик Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)

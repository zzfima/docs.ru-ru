---
title: Практическое руководство. Настройка каналов с использованием поставщика Entity Framework (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: fd16272e-36f2-415e-850e-8a81f2b17525
ms.openlocfilehash: 16c3741068d19fb55d8acfd28e4f83df633b0b09
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569158"
---
# <a name="how-to-customize-feeds-with-the-entity-framework-provider-wcf-data-services"></a>Практическое руководство. Настройка каналов с использованием поставщика Entity Framework (службы данных WCF)
WCF Data Services позволяет настроить сериализацию Atom в ответе службы данных, чтобы свойства сущности могли быть сопоставлены с неиспользуемыми элементами, определенными в протоколе AtomPub. Этот раздел показывает, как настроить атрибуты сопоставления типов сущностей в модели данных, определенных в файле EDMX, с помощью поставщика Entity Framework. Дополнительные сведения см. в разделе [Настройка веб-канала](feed-customization-wcf-data-services.md).  
  
 В этом разделе мы вручную изменим сформированный программой файл EDMX, содержащий модель данных. Поскольку расширения модели данных не поддерживаются конструктором сущностей, необходимо вручную модифицировать этот файл. Дополнительные сведения о EDMX-файле, создаваемом EDM инструментами, см. в разделе [Общие сведения о файле EDMX (Entity Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)). Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и классы данных клиента создаются при завершении [краткого руководства по WCF Data Services](quickstart-wcf-data-services.md).  
  
### <a name="to-manually-modify-the-northwindedmx-file-to-add-feed-customization-attributes"></a>Изменение файла Northwind.edmx вручную для добавления атрибутов настройки каналов  
  
1. В **Обозреватель решений**щелкните правой кнопкой мыши файл `Northwind.edmx` и выберите команду **Открыть с помощью**.  
  
2. В диалоговом окне **Открыть с помощью-Northwind. EDMX** выберите **XML-редактор**и нажмите кнопку **ОК**.  
  
3. Найдите элемент `ConceptualModels` и замените имеющийся тип сущности `Customers` на элемент, содержащий атрибуты сопоставления для настройки канала.  
  
     [!code-xml[Astoria Custom Feeds#EdmFeedCustomers](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/northwind.csdl#edmfeedcustomers)]  
  
4. Сохраните изменения и закройте файл Northwind.edmx.  
  
5. Используемых Щелкните правой кнопкой мыши файл Northwind. edmx и выберите пункт **запустить настраиваемый инструмент**.  
  
     При этом будет повторно сформирован файл уровня объектов, который может потребоваться.  
  
6. Перекомпилируйте проект.  
  
## <a name="example"></a>Пример  
 Предыдущий пример возвращает следующий результат для URI `http://myservice/Northwind.svc/Customers('ALFKI')`.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/edmfeedresult.xml#edmfeedresult)]  
  
## <a name="see-also"></a>См. также:

- [Поставщик Entity Framework](entity-framework-provider-wcf-data-services.md)

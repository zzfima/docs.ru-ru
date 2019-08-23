---
title: <wsdlImporters>
ms.date: 03/30/2017
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
ms.openlocfilehash: da9ab00c86e7f2657bfc28724d328ccbbc6957b1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915163"
---
# <a name="wsdlimporters"></a>\<Всдлимпортерс >
Этот элемент конфигурации указывает всех импортеров WSDL, импортирующих метаданные на языке WSDL 1.1 с вложениями WS-Policy. Каждый дочерний элемент —`wsdlImporter`это < >, который указывает способ импорта метаданных, а также преобразования этих данных в различные классы, представляющие сведения о контрактах и конечных точках. Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования. Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>
- <xref:System.ServiceModel.Description.MetadataImporter>
- <xref:System.ServiceModel.Description.WsdlImporter>
- [Конфигурация клиента WCF](../../../wcf/feature-details/client-configuration.md)
- [Клиенты](../../../wcf/feature-details/clients.md)

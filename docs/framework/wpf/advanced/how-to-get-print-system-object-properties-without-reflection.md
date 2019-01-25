---
title: Как выполнить Получение свойств объекта системы печати без отражения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: b081586d201bed537c086447c4ddb116f179fbca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693257"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a>Как выполнить Получение свойств объекта системы печати без отражения
Использование отражения для перечисления свойств (и типов этих свойств) в объекте может снизить производительность приложения. <xref:System.Printing.IndexedProperties> Пространство имен предоставляет средства для получение этой информации с помощью отражения.  
  
## <a name="example"></a>Пример  
 Ниже приведены действия для этого.  
  
1.  Создайте экземпляр типа. В следующем примере тип является <xref:System.Printing.PrintQueue> тип, который поставляется с Microsoft .NET Framework, но почти идентичный код должен работать для типов, производных от <xref:System.Printing.PrintSystemObject>.  
  
2.  Создание <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> из типа <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>. <xref:System.Collections.DictionaryEntry.Value%2A> Каждой записи в этом словаре является объектом одного из типов, производных от <xref:System.Printing.IndexedProperties.PrintProperty>.  
  
3.  Перечисление элементов словаря. Для каждого из них выполните следующие действия.  
  
4.  Приведите значение каждого элемента в <xref:System.Printing.IndexedProperties.PrintProperty> и использовать его для создания <xref:System.Printing.IndexedProperties.PrintProperty> объекта.  
  
5.  Получить тип <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> каждого из <xref:System.Printing.IndexedProperties.PrintProperty> объекта.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Printing.IndexedProperties.PrintProperty>
- <xref:System.Printing.PrintSystemObject>
- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [Документы в WPF](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [Общие сведения о печати](../../../../docs/framework/wpf/advanced/printing-overview.md)

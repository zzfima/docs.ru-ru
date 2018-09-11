---
title: Доступ ко внедренным объектам с помощью автоматизации пользовательского интерфейса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- embedded objects, accessing
- accessing embedded objects
- UI Automation, accessing embedded objects
ms.assetid: a5b513ec-7fa6-4460-869f-c18ff04f7cf2
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 05f9359aa055019b517abb1b7c86ca386d630e41
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262429"
---
# <a name="access-embedded-objects-using-ui-automation"></a>Доступ ко внедренным объектам с помощью автоматизации пользовательского интерфейса
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Для получения последних сведений о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], см. в разделе [API автоматизации Windows: модели автоматизации пользовательского интерфейса](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 В этом разделе показано, как можно использовать [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] для представления объектов, внедренных в содержимое элемента управления "Текст".  
  
> [!NOTE]
>  Внедренные объекты могут включать изображения, гиперссылки, кнопки, таблицы или элементы ActiveX.  
  
 Внедренные объекты считаются дочерними элементами поставщика текста [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Это позволяет предоставлять их через ту же древовидную структуру модели автоматизации пользовательского интерфейса, что и все остальные элементы [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] . Функциональные возможности в свою очередь предоставляются с помощью шаблонов элементов управления, которые обычно требуются типом элемента управления внедренных объектов (например, поскольку гиперссылки основаны на тексте, они будут поддерживать <xref:System.Windows.Automation.TextPattern>).  
  
 ![Внедренные объекты в текстовом контейнере. ](../../../docs/framework/ui-automation/media/uia-textpattern-embeddedobjects.PNG "UIA_TextPattern_EmbeddedObjects")  
Образец документа с текстовым содержимым («знаете ли вы?» ...) и двумя внедренными объектами (изображением Кита и гиперссылкой), используется в качестве цели для примеров кода.  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется извлечение коллекции внедренных объектов из поставщика текста [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Для образца документа, приведенного во введении, будет возвращено два объекта (элемент изображения и текстовый элемент).  
  
> [!NOTE]
>  Элемент изображения должен иметь некоторый связанный с ним встроенный текст, описывающий изображение, обычно в его свойстве <xref:System.Windows.Automation.AutomationElement.NameProperty> (например, "Синий кит".). Однако если получен текстовый диапазон, перекрывающий этот объект-изображение, в текстовом потоке не возвращается ни это изображение, ни его описательный текст.  
  
 [!code-csharp[FindText#StartApp](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#startapp)]
 [!code-vb[FindText#StartApp](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#startapp)]  
[!code-csharp[FindText#FindTextProvider](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#findtextprovider)]
[!code-vb[FindText#FindTextProvider](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#findtextprovider)]  
[!code-csharp[FindText#GetChildren](../../../samples/snippets/csharp/VS_Snippets_Wpf/FindText/CSharp/SearchWindow.cs#getchildren)]
[!code-vb[FindText#GetChildren](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindText/VisualBasic/SearchWindow.vb#getchildren)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется получение текстового диапазона из внедренного объекта в поставщике текста [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] . Полученный текстовый диапазон является пустым диапазоном, где за начальной точкой следует "... океан.(пространство)", и перед конечной точкой стоит закрывающая точка ".", представляющая внедренную гиперссылку (как показано на рисунке во введении). Несмотря на то что это пустой диапазон, он не считается вырожденным диапазоном, так как содержит ненулевой промежуток.  
  
> [!NOTE]
>  <xref:System.Windows.Automation.TextPattern> может получить текстовый внедренный объект как гиперссылку; однако для предоставления полной функциональности внедренного объекта из него должен быть получен дополнительный <xref:System.Windows.Automation.TextPattern> .  
  
 [!code-csharp[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#getrangefromchild)]
 [!code-vb[UIATextPattern_snip#GetRangeFromChild](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIATextPattern_snip/VisualBasic/SearchWindow.vb#getrangefromchild)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об объекте TextPattern модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-textpattern-overview.md)  
 [Общие сведения о шаблонах элементов управления модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)  
 [Шаблоны элементов управления модели автоматизации пользовательского интерфейса для клиентов](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)  
 [Добавление содержимого в текстовое поле с помощью модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/add-content-to-a-text-box-using-ui-automation.md)  
 [Поиск и выделение текста с помощью модели автоматизации пользовательского интерфейса](../../../docs/framework/ui-automation/find-and-highlight-text-using-ui-automation.md)

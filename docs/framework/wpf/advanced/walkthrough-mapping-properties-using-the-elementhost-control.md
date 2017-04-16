---
title: "Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ElementHost - элемент управления, сопоставление свойств"
  - "сопоставление свойств"
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost
В этом руководстве описывается порядок использования свойства <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> для сопоставления свойств [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с соответствующими свойствами элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В этом пошаговом руководстве демонстрируется выполнение следующих задач.  
  
-   Создание проекта.  
  
-   Определение нового сопоставления свойства.  
  
-   Удаление сопоставления свойства по умолчанию.  
  
-   Расширение сопоставления свойства по умолчанию.  
  
 Полный пример кода для задач, приведенных в этом обзоре, см. на странице [Пример сопоставления свойств с помощью элемента управления ElementHost](http://go.microsoft.com/fwlink/?LinkID=160018).  
  
 После изучения этого раздела вы сможете сопоставлять свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с соответствующими свойствами элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
## Обязательные компоненты  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## Создание проекта  
  
#### Создание проекта  
  
1.  Создайте проект приложения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] с именем `PropertyMappingWithElementHost`.  Дополнительные сведения см. в разделе [How to: Create a Windows Application Project](http://msdn.microsoft.com/ru-ru/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В обозревателе решений добавьте ссылки на следующие сборки [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
3.  Скопируйте следующий код в начало файла кода `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  Откройте форму `Form1` в конструкторе Windows Forms.  Дважды щелкните форму, чтобы добавить обработчик событий <xref:System.Windows.Forms.Form.Load>.  
  
5.  Вернитесь в конструктор Windows Forms и добавьте обработчик событий для события <xref:System.Windows.Forms.Control.Resize> формы.  Дополнительные сведения см. в разделе [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/ru-ru/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
6.  Объявите поле <xref:System.Windows.Forms.Integration.ElementHost> в классе `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## Определение новых сопоставлений свойств  
 Элемент управления <xref:System.Windows.Forms.Integration.ElementHost> предоставляет несколько сопоставлений свойств по умолчанию.  Чтобы добавить новое сопоставление свойства, следует вызвать метод <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> для свойства <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### Определение новых сопоставлений свойств  
  
1.  Скопируйте следующий код в определение класса `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     Метод `AddMarginMapping` используется для добавления нового сопоставления для свойства <xref:System.Windows.Forms.Control.Margin%2A>.  
  
     Метод `OnMarginChange` используется для преобразования свойства <xref:System.Windows.Forms.Control.Margin%2A> в свойство [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A>.  
  
2.  Скопируйте следующий код в определение класса `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     Метод `AddRegionMapping` используется для добавления нового сопоставления для свойства <xref:System.Windows.Forms.Control.Region%2A>.  
  
     Метод `OnRegionChange` используется для преобразования свойства <xref:System.Windows.Forms.Control.Region%2A> в свойство [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A>.  
  
     Метод `Form1_Resize` используется для обработки события <xref:System.Windows.Forms.Control.Resize> формы и изменения размеров области отсечения в соответствии с размером размещенного элемента.  
  
## Удаление сопоставления свойства по умолчанию  
 Чтобы удалить сопоставление свойства по умолчанию, вызовите метод <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> для свойства <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> элемента управления <xref:System.Windows.Forms.Integration.ElementHost>.  
  
#### Удаление сопоставления свойства по умолчанию  
  
-   Скопируйте следующий код в определение класса `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     Метод `RemoveCursorMapping` используется для удаления сопоставления по умолчанию для свойства <xref:System.Windows.Forms.Control.Cursor%2A>.  
  
## Расширение сопоставления свойства по умолчанию  
 Можно использовать сопоставление свойства по умолчанию, а также расширить его с помощью собственного сопоставления.  
  
#### Расширение сопоставления свойства по умолчанию  
  
-   Скопируйте следующий код в определение класса `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     Метод `ExtendBackColorMapping` используется для добавления пользовательского преобразователя свойств к существующему сопоставлению свойства <xref:System.Windows.Forms.Control.BackColor%2A>.  
  
     Метод `OnBackColorChange` используется для присваивания определенного изображения свойству <xref:System.Windows.Controls.Control.Background%2A> размещенного элемента управления.  Метод `OnBackColorChange` вызывается после применения сопоставления свойства по умолчанию.  
  
## Инициализация сопоставлений свойств  
  
#### Инициализация сопоставления свойств  
  
1.  Скопируйте следующий код в определение класса `Form1`.  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     Метод `Form1_Load` используется для обработки события <xref:System.Windows.Forms.Form.Load> и выполнения следующей инициализации.  
  
    -   Создание элемента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button>.  
  
    -   Вызов методов, ранее определенных в пошаговом руководстве, для настройки сопоставлений свойств.  
  
    -   Назначение начальных значений сопоставленным свойствам.  
  
2.  Нажмите клавишу F5 для построения и выполнения приложения.  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)   
 [Конструктор WPF](http://msdn.microsoft.com/ru-ru/c6c65214-8411-4e16-b254-163ed4099c26)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
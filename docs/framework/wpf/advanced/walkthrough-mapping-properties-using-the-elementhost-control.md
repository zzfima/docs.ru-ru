---
title: "Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 030183e77a141036416a3bcb8a4c4018df0a7e65
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost
В этом пошаговом руководстве показано, как использовать <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> свойство для сопоставления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] свойства соответствующим свойствам размещенных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемента.  
  
 В данном пошаговом руководстве представлены следующие задачи.  
  
-   Создание проекта.  
  
-   Определение нового сопоставления свойства.  
  
-   Удаление сопоставления свойства по умолчанию.  
  
-   Расширение сопоставления свойства по умолчанию.  
  
 Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [сопоставление свойств с помощью пример элемента управления ElementHost](http://go.microsoft.com/fwlink/?LinkID=160018).  
  
 Когда вы закончите, можно для сопоставления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] свойства соответствующее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства элемента.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)].  
  
## <a name="creating-the-project"></a>Создание проекта  
  
#### <a name="to-create-the-project"></a>Создание проекта  
  
1.  Создание [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] проект приложения с именем `PropertyMappingWithElementHost`. Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения WPF](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  В обозревателе решений добавьте ссылки на следующие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сборки.  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
3.  Скопируйте следующий код в верхнюю часть `Form1` файл кода.  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  Откройте `Form1` в конструкторе Windows Forms. Дважды щелкните форму, чтобы добавить обработчик событий для <xref:System.Windows.Forms.Form.Load> события.  
  
5.  Вернитесь к конструктору Windows Forms и добавьте обработчик событий для формы <xref:System.Windows.Forms.Control.Resize> событий. Дополнительные сведения см. в разделе [как: создание событий обработчики с помощью конструктора](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).  
  
6.  Объявите <xref:System.Windows.Forms.Integration.ElementHost> в `Form1` класса.  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a>Определение новых сопоставлений свойств  
 <xref:System.Windows.Forms.Integration.ElementHost> Управления предоставляет несколько по умолчанию сопоставления свойств. Добавить новое сопоставление свойства путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> метод <xref:System.Windows.Forms.Integration.ElementHost> элемента управления <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.  
  
#### <a name="to-define-new-property-mappings"></a>Для определения новых сопоставлений свойств  
  
1.  Скопируйте следующий код в определение `Form1` класса.  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     `AddMarginMapping` Метод добавляет новое сопоставление для <xref:System.Windows.Forms.Control.Margin%2A> свойства.  
  
     `OnMarginChange` Метод переводит <xref:System.Windows.Forms.Control.Margin%2A> свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> свойство.  
  
2.  Скопируйте следующий код в определение `Form1` класса.  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     `AddRegionMapping` Метод добавляет новое сопоставление для <xref:System.Windows.Forms.Control.Region%2A> свойства.  
  
     `OnRegionChange` Метод переводит <xref:System.Windows.Forms.Control.Region%2A> свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> свойство.  
  
     `Form1_Resize` Метод обрабатывает формы <xref:System.Windows.Forms.Control.Resize> событий и размеров области отсечения для соответствия размещаемому элементу.  
  
## <a name="removing-a-default-property-mapping"></a>Удаление сопоставления свойства по умолчанию  
 Удалить сопоставление свойства по умолчанию путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> метод <xref:System.Windows.Forms.Integration.ElementHost> элемента управления <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.  
  
#### <a name="to-remove-a-default-property-mapping"></a>Удаление сопоставления свойства по умолчанию  
  
-   Скопируйте следующий код в определение `Form1` класса.  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     `RemoveCursorMapping` Метод удаляет сопоставление по умолчанию для <xref:System.Windows.Forms.Control.Cursor%2A> свойства.  
  
## <a name="extending-a-default-property-mapping"></a>Расширение сопоставления свойства по умолчанию  
 Вы можете использовать сопоставление свойства по умолчанию, а также расширить его с помощью собственного сопоставления.  
  
#### <a name="to-extend-a-default-property-mapping"></a>Расширение сопоставления свойства по умолчанию  
  
-   Скопируйте следующий код в определение `Form1` класса.  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     `ExtendBackColorMapping` Метод добавляет пользовательский преобразователь свойств для существующего <xref:System.Windows.Forms.Control.BackColor%2A> сопоставление свойств.  
  
     `OnBackColorChange` Метод назначает конкретный образ размещенного элемента управления <xref:System.Windows.Controls.Control.Background%2A> свойство. `OnBackColorChange` Метод вызывается после применения сопоставления свойства по умолчанию.  
  
## <a name="initializing-your-property-mappings"></a>Инициализация сопоставлений свойств  
  
#### <a name="to-initialize-your-property-mappings"></a>Инициализация сопоставлений свойств  
  
1.  Скопируйте следующий код в определение `Form1` класса.  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     `Form1_Load` Метод обрабатывает <xref:System.Windows.Forms.Form.Load> событие и выполняет следующую инициализацию.  
  
    -   Создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> элемента.  
  
    -   Вызывает методы, ранее определенные в руководстве, для настройки сопоставлений свойств.  
  
    -   Присваивает начальные значения сопоставленным свойствам.  
  
2.  Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Сопоставление свойств Windows Forms и WPF](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [Конструктор WPF](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)

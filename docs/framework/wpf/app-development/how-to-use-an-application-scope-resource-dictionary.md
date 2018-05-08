---
title: Практическое руководство. Использование словаря ресурсов области определения приложения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dictionaries [WPF], resource
- resource dictionaries [WPF], application-scope
- application-scope resource dictionaries
ms.assetid: 53857682-bd2c-4f2c-8f25-1307d0b451a2
ms.openlocfilehash: a42fee8ad31dcc02459711fc51e8611e0e8cd012
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Практическое руководство. Использование словаря ресурсов области определения приложения
В этом примере показано, как определить и использовать пользовательский словарь ресурсов области определения приложения.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Application> предоставляет хранилище области приложения для общих ресурсов: <xref:System.Windows.Application.Resources%2A>. По умолчанию <xref:System.Windows.Application.Resources%2A> с помощью экземпляра инициализируется свойство <xref:System.Windows.ResourceDictionary> типа. Этот экземпляр используется при получение и задание свойств области приложения с помощью <xref:System.Windows.Application.Resources%2A>. Дополнительные сведения см. в разделе [как: получение и задание ресурсов области приложения](http://msdn.microsoft.com/library/39e0420c-c9fc-47dc-8956-fdd95b214095).
  
 Если имеется несколько ресурсов, которые можно задать с помощью <xref:System.Windows.Application.Resources%2A>, словарь пользовательских ресурсов вместо этого можно использовать для хранения этих ресурсов и установки <xref:System.Windows.Application.Resources%2A> с ним вместо него. Ниже показано, как объявить словарь пользовательских ресурсов с помощью XAML.
  
 [!code-xaml[HOWTOResourceDictionaries#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Замена целых словарей ресурсов с помощью <xref:System.Windows.Application.Resources%2A> позволяет поддерживать темы области приложения, когда каждая тема инкапсулируется одним словарем ресурсов. В следующем примере показано, как задать свойство <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Далее показано, как получить ресурсы области приложения из словаря ресурсов, предоставляемых <xref:System.Windows.Application.Resources%2A> в XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 Ниже показано, как можно получить ресурсы в коде.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 Существуют два аспекта, чтобы сделать при использовании <xref:System.Windows.Application.Resources%2A>. Во-первых, словарь *ключ* является объектом, поэтому необходимо использовать один и тот же экземпляр объекта при установке и получении значения свойства. (Обратите внимание, что при использовании строки в ключе учитывается регистр.) Во-вторых, словарь *значение* является объектом, поэтому необходимо преобразовать значение в требуемый тип при получении значения свойства.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.ResourceDictionary>  
 <xref:System.Windows.Application.Resources%2A>  
 [Ресурсы XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [Объединенные словари ресурсов](../../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md)

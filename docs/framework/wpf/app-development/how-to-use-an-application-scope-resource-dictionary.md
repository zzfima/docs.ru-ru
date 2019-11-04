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
ms.openlocfilehash: 5bfb3ed0304598a5acf4b7682bf4a4169c5153d1
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459793"
---
# <a name="how-to-use-an-application-scope-resource-dictionary"></a>Практическое руководство. Использование словаря ресурсов области определения приложения
В этом примере показано, как определить и использовать пользовательский словарь ресурсов области определения приложения.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Application> предоставляет хранилище области приложения для общих ресурсов: <xref:System.Windows.Application.Resources%2A>. По умолчанию свойство <xref:System.Windows.Application.Resources%2A> инициализируется экземпляром типа <xref:System.Windows.ResourceDictionary>. Этот экземпляр используется при получении и установке свойств области действия приложения с помощью <xref:System.Windows.Application.Resources%2A>. Дополнительные сведения см. [в разделе как получить и задать ресурс области приложения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348547(v=vs.100)).
  
 При наличии нескольких ресурсов, которые вы задаете с помощью <xref:System.Windows.Application.Resources%2A>, вместо этого можно использовать настраиваемый словарь ресурсов для хранения этих ресурсов и установки <xref:System.Windows.Application.Resources%2A>. Ниже показано, как объявить пользовательский словарь ресурсов с помощью XAML.
  
 [!code-xaml[HOWTOResourceDictionaries#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MyResourceDictionary.xaml#1)]  
  
 Переключение всех словарей ресурсов с помощью <xref:System.Windows.Application.Resources%2A> позволяет поддерживать темы области приложения, в которых каждая тема инкапсулируется одним словарем ресурсов. В следующем примере показано, как задать свойство <xref:System.Windows.ResourceDictionary>.  
  
 [!code-xaml[HOWTOResourceDictionaries#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/App.xaml#2)]  
  
 Ниже показано, как можно получить ресурсы области приложения из словаря ресурсов, предоставляемого <xref:System.Windows.Application.Resources%2A> в XAML.  
  
 [!code-xaml[HOWTOResourceDictionaries#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml#4)]  
  
 Ниже показано, как можно получить ресурсы в коде.  
  
 [!code-csharp[HOWTOResourceDictionaries#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToResourceDictionaries/CSharp/MainWindow.xaml.cs#3)]
 [!code-vb[HOWTOResourceDictionaries#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToResourceDictionaries/VB/MainWindow.xaml.vb#3)]  
  
 При использовании <xref:System.Windows.Application.Resources%2A>следует учитывать два фактора. Во-первых, *ключ* словаря является объектом, поэтому при установке и получении значения свойства необходимо использовать точно такой же экземпляр объекта. (Обратите внимание, что при использовании строки ключ учитывает регистр.) Во-вторых, *значение* словаря является объектом, поэтому необходимо преобразовать значение в нужный тип при получении значения свойства.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.ResourceDictionary>
- <xref:System.Windows.Application.Resources%2A>
- [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Объединенные словари ресурсов](../advanced/merged-resource-dictionaries.md)

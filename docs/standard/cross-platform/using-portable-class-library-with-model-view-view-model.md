---
title: Использование переносимой библиотеки классов с шаблоном "модель-представление-модель представления"
ms.date: 07/18/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3aa18d4498bcdcc3737311473b4736545b184395
ms.sourcegitcommit: 11deacc8ec9f229ab8ee3cd537515d4c2826515f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2019
ms.locfileid: "66003786"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a>Использование переносимой библиотеки классов с шаблоном "модель-представление-модель представления"
Можно использовать .NET Framework [переносимой библиотеки классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) реализовать шаблон модель-представление-View Model (MVVM) и совместного использования сборок на нескольких платформах.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM — это шаблон приложения, который изолирует интерфейс пользователя от основной бизнес-логики. Можно реализовать классы модели и представления модели в [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проекта в Visual Studio 2012, а затем создать представления, которые настраиваются для различных платформ. Такой подход позволяет создавать модель и бизнес-логику данных только один раз и использовать этот код в платформе .NET Framework, приложениях Silverlight, Windows Phone и [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], как показано на следующей иллюстрации.

 ![Показывает переносимой библиотеки классов с MVVM совместного использования сборок на платформах.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 В этом разделе не предоставляет общие сведения о шаблоне MVVM. Он только предоставляет сведения об использовании [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] для реализации MVVM. Дополнительные сведения о шаблоне MVVM см. в разделе [MVVM быстрого запуска с помощью 5.0 библиотеку Prism для WPF](https://docs.microsoft.com/previous-versions/msp-n-p/gg430857(v=pandp.40)).

## <a name="classes-that-support-mvvm"></a>Классы, поддерживающие MVVM
 Отметив [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight или Windows Phone 7.5 для вашей [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проект, следующие классы доступны для реализации шаблона MVVM:

- Класс <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType>

- Класс <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType>

- Класс <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType>

- Класс <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType>

- Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType>

- Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType>

- Класс <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType>

- Класс <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType>

- Класс <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType>

- Класс <xref:System.Windows.Input.ICommand?displayProperty=nameWithType>

- Все классы в <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> пространства имен

## <a name="implementing-mvvm"></a>Реализации MVVM
 Для реализации MVVM, вы обычно создают модель и модель представления в [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проекта, так как [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проект не может ссылаться на проект непереносимые. Модели и модели представления может быть в одном проекте или в виде отдельных проектов. Если вы используете отдельные проекты, добавьте ссылку из проекта модели представления в проект модели.

 После компиляции модели и просматривать проекты модели, можно ссылаться на эти сборки в приложении, которая содержит представление. Если представление взаимодействует только с помощью модели представления, необходимо ссылаться на сборку, содержащую модели представления.

### <a name="model"></a>Модель
 В примере показан класс упрощенной модели, которые могут располагаться в [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проекта.

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 В примере показан простой способ заполнения, извлечения и обновления данных в [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] проекта. В реальном приложении можно извлечь данные из источника, например службы Windows Communication Foundation (WCF).

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a>Модель представления
 Базовый класс для представления моделей часто добавляется при реализации шаблона MVVM. В следующем примере базового класса.

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 Реализация <xref:System.Windows.Input.ICommand> интерфейс часто используется с помощью шаблона MVVM. В следующем примере показана реализация интерфейса <xref:System.Windows.Input.ICommand>.

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 В примере показан упрощенный вид модели.

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>Просмотр  
 Из [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] приложения, [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложения, приложения Silverlight или приложения Windows Phone 7.5, могут ссылаться на сборки, содержащей проекты модели модель и представление.  Затем создается представление, которое взаимодействует с моделью представления. В примере показан упрощенный приложение Windows Presentation Foundation (WPF), которое извлекает и обновляет данные из модели представления. В Silverlight, Windows Phone, можно создать похожих представлениях или [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] приложений.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>См. также

- [Переносимая библиотека классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)

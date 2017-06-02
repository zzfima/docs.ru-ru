---
title: "Использование переносимой библиотеки классов с шаблоном &quot;модель-представление-модель представления&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Переносимая библиотека классов [.NET Framework] и MVVM"
  - "MVVM и переносимая библиотека классов"
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
caps.latest.revision: 17
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 17
---
# Использование переносимой библиотеки классов с шаблоном &quot;модель-представление-модель представления&quot;
Вы можете использовать [Переносимые библиотеки классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) для реализации шаблона Model\-View\-View Model \(MVVM\) и совместного использования сборки на нескольких платформах.  
  
 MVVM \- это шаблон приложения, который изолирует интерфейс пользователя от основной бизнес\-логики.  В частности, можно реализовать классы модели и модели представления в проекте [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], а затем создать представления, которые учитывают особенности разных платформ.  Такой подход позволяет создавать модель и бизнес\-логику данных только один раз, и использовать этот код в платформе .NET Framework, приложениях Silverlight, Windows Phone и Windows [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], как показано на следующей иллюстрации.  
  
 ![Переносится со схемой MVVM](../../../docs/standard/cross-platform/media/portablemvvmdiagram.png "PortableMVVMdiagram")  
  
 Этот раздел не содержит общих сведений о шаблоне MVVM.  Он предоставляет сведения только о том, как использовать [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] для реализации MVVM.  Дополнительные сведения о шаблоне MVVM см. в разделе [MVVM Quickstart](http://go.microsoft.com/fwlink/?LinkId=234934).  
  
## Классы, поддерживающие MVVM  
 Если для проекта [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] предназначены [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)], Silverlight или Windows Phone 7.5, то для реализации шаблона MVVM доступны следующие классы:  
  
-   Класс <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=fullName>  
  
-   Класс <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=fullName>  
  
-   Класс <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=fullName>  
  
-   Класс <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=fullName>  
  
-   Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=fullName>  
  
-   Класс <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=fullName>  
  
-   Класс <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=fullName>  
  
-   Класс <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=fullName>  
  
-   Класс <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=fullName>  
  
-   Класс <xref:System.Windows.Input.ICommand?displayProperty=fullName>  
  
-   Все классы в пространстве имен <xref:System.ComponentModel.DataAnnotations?displayProperty=fullName> .  
  
## Реализация MVVM  
 Для реализации MVVM обычно и модель, и модель представления создаются в проекте [!INCLUDE[net_portable](../../../includes/net-portable-md.md)], поскольку проект [!INCLUDE[net_portable](../../../includes/net-portable-md.md)] не может ссылаться на непереносимые проекты.  Модель и модель представления могут находиться в одном и том же или же в разных проектах.  При использовании отдельных проектов добавьте ссылку из проекта модели представления на проект модели.  
  
 Скомпилировав проекты модели и модели представления, можно ссылаться на эти сборки в приложении, которое содержит представление.  Если представление работает только с моделью представления, то необходимо ссылаться только на сборку, которая содержит модель представления.  
  
### Модель  
 В следующем примере показан класс упрощенной модели, который может находиться в проекте [!INCLUDE[net_portable](../../../includes/net-portable-md.md)].  
  
 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]  
  
 В следующем примере показан простой способ заполнения, получения и обновления данных в проектах [!INCLUDE[net_portable](../../../includes/net-portable-md.md)].  В реальном приложении данные будут получены из источника, подобного службе Windows Communication Foundation \(WCF\).  
  
 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]  
  
### Модель представления  
 Базовый класс для модели представления часто добавляется при реализации шаблона MVVM.  В следующем примере показан базовый класс.  
  
 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]  
  
 Реализация интерфейса <xref:System.Windows.Input.ICommand> часто используется с шаблоном MVVM.  В следующем примере показана реализация интерфейса <xref:System.Windows.Input.ICommand>.  
  
 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]  
  
 В следующем примере показана упрощенная модель представления.  
  
 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### Просмотр  
 Из приложения [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], приложения [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)], приложения на основе Silverlight или приложения Windows Phone 7.5 можно ссылаться на сборку, которая содержит проекты модели и модели представления.  Затем создается представление, которое взаимодействует с моделью представления.  В следующем примере показан упрощенное приложение Windows Presentation Foundation \(WPF\), получающее и обновляющее данные из модели представления.  Можно создавать схожие представления в Silverlight, Windows Phone или приложениях [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)].  
  
 [!code-xml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## См. также  
 [Переносная библиотека классов](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md)
---
title: "GetCustomUI | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "пользовательские сообщения об ошибках [WPF]"
  - "GetCustomUI - метод"
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# GetCustomUI
Вызывается программой PresentationHost.exe для получения пользовательских сообщений о ходе процесса м ошибках от узла \(если эта возможность реализована\).  
  
## Синтаксис  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### Параметры  
 `pwzProgressAssemblyName`  
  
 \[выходной\] Указатель на сборку, содержащую пользовательский интерфейс хода процесса, предоставленный узелом.  
  
 `pwzProgressClassName`  
  
 \[выходной\] Имя класса, являющегося пользовательским интерфейсом хода процесса, предоставленным узелом — предпочтительно файла [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] с <xref:System.Windows.Controls.Page>, который является его элементом верхнего уровня.  Этот класс содержится в сборке, указанной `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 \[выходной\] Указатель на сборку, содержащую пользовательский интерфейс ошибок, предоставленный узелом.  
  
 `pwzErrorClassName`  
  
 \[выходной\] Имя класса, являющегося пользовательским интерфейсом ошибок, предоставленным узелом — предпочтительно файла XAML с <xref:System.Windows.Controls.Page>, который является его элементом верхнего уровня.  Этот класс содержится в сборке, указанной `pwzErrorAssemblyName`.  
  
## Значение свойства или возвращаемое значение  
 HRESULT: Ignored.  
  
## Заметки  
 Ведущее приложение может иметь особую тему, которая не соответствует пользовательскому интерфейсу PresentationHost.exe по умолчанию.  В этом случае ведущее приложение может реализовать [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md), чтобы вернуть интерфейсы хода процесса и ошибок в PresentationHost.exe.  PresentationHost.exe всегда будет вызывать [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) перед использованием своих пользовательских интерфейсов по умолчанию.  
  
 Эта функция вызывается один раз во время инициализации PresentationHost.  
  
## См. также  
 [Интерфейс IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
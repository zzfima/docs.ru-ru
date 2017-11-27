---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f3c101ad13df9b99a2d872bac8783baed8b4b9a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="getcustomui"></a>GetCustomUI
Вызывается PresentationHost.exe для получения пользовательских хода выполнения и сообщения об ошибках с узла, если реализовано.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a>Параметры  
 `pwzProgressAssemblyName`  
  
 [out] Указатель на сборку, содержащую пользовательский интерфейс узла предоставленный хода выполнения.  
  
 `pwzProgressClassName`  
  
 [out] Имя класса, интерфейс пользователя хода выполнения на указанный узел меньшее [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] , что файл <xref:System.Windows.Controls.Page> — его элемент верхнего уровня. Этот класс находится в сборке, который задается параметром `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 [out] Указатель на сборку, содержащую пользовательский интерфейс об узле.  
  
 `pwzErrorClassName`  
  
 [out] Имя класса пользователя об узле интерфейса, предпочтительно XAML-файл с <xref:System.Windows.Controls.Page> — его элемент верхнего уровня. Этот класс находится в сборке, который задается параметром `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 Значение HRESULT: игнорируется.  
  
## <a name="remarks"></a>Примечания  
 Ведущее приложение может иметь особую тему, которая может не соответствовать PresentationHost.exe по умолчанию пользовательских интерфейсов. Если это так, можно реализовать ведущее приложение [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) для возврата хода выполнения и ошибки пользовательские интерфейсы PresentationHost.exe. Всегда будет вызывать PresentationHost.exe [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) перед использованием его пользовательские интерфейсы по умолчанию.  
  
 Эта функция вызывается один раз во время инициализации PresentationHost элемента.  
  
## <a name="see-also"></a>См. также  
 [IWpfHostSupport](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)

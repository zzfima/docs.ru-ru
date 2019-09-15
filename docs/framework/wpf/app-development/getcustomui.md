---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: a9c4c9d597f5cc1b172213d49a3dd5b8f1c1f671
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991376"
---
# <a name="getcustomui"></a>GetCustomUI
Вызывается PresentationHost. exe для получения настраиваемого хода выполнения и сообщений об ошибках с узла, если они реализованы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzProgressAssemblyName`  
  
 заполняет Указатель на сборку, содержащую пользовательский интерфейс хода выполнения.  
  
 `pwzProgressClassName`  
  
 заполняет Имя класса, предоставляемого ведущим пользовательским интерфейсом выполнения, предпочтительнее [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] файл с <xref:System.Windows.Controls.Page> элементом верхнего уровня. Этот класс находится в сборке, указанной в параметре `pwzProgressAssemblyName`.  
  
 `pwzErrorAssemblyName`  
  
 заполняет Указатель на сборку, содержащую пользовательский интерфейс ошибки, предоставляемый узлом.  
  
 `pwzErrorClassName`  
  
 заполняет Имя класса, предоставляемого ведущим пользовательским интерфейсом ошибок, предпочтительнее XAML-файл с <xref:System.Windows.Controls.Page> элементом верхнего уровня. Этот класс находится в сборке, указанной в параметре `pwzErrorAssemblyName`.  
  
## <a name="property-valuereturn-value"></a>Значение свойства, возвращаемое значение  
 HRESULT: Не обрабатывается.  
  
## <a name="remarks"></a>Примечания  
 Ведущее приложение может иметь определенную тему, которая может не соответствовать интерфейсу пользователя PresentationHost. exe по умолчанию. В этом случае ведущее приложение может реализовать [GetCustomUI](getcustomui.md) для возврата сведений о ходе выполнения и ошибок пользовательского интерфейса в PresentationHost. exe. PresentationHost. exe всегда будет вызывать [GetCustomUI](getcustomui.md) перед использованием пользовательских интерфейсов по умолчанию.  
  
 Эта функция вызывается один раз во время инициализации PresentationHost.  
  
## <a name="see-also"></a>См. также

- [IWpfHostSupport](iwpfhostsupport.md)

---
title: "Директива x:Property"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 618555a8-c893-455c-810f-ac54cd24ef10
caps.latest.revision: "6"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 36e464f9a45d737317192b2588473e90ae44a456
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="xproperty-directive"></a>Директива x:Property
Объявляет свойство XAML в разметке.  
  
## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML  
  
```  
<object x:Class="className">  
  <x:Members>  
    <x:Property Name="propertyName" Type="propertyType/>  
    additionalProperties  
  </x:Members>  
</object>  
```  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`className`|Имя класса резервирования или разделяемого класса для рабочей среды XAML.|  
|`propertyName`|Имя члена определяемого свойства.|  
|`propertyType`|Имя типа (или другая строковая форма, специфичная для платформы), указывающее тип этого свойства.|  
  
## <a name="remarks"></a>Примечания  
 В реализации служб XAML платформы .NET Framework `x:Property` не имеет прямое резервирование типа, но поддерживается классом <xref:System.Windows.Markup.PropertyDefinition>. В потоке узлов XAML элемент `x:Property` представляется как член с именем `Property` из пространства имен XAML языка XAML. Член `Property` хранит атрибуты, объявленные в разметке.  
  
 Значения `Name` и `Type` не назначаются на уровне служб XAML .NET Framework. Они хранятся в исходном потоке узлов XAML как строковые значения для последующей интерпретации в соответствии с правилами, которые могут быть наложены конкретными платформами. Эти значения могут выравниваться по значениям имени XAML и типа XAML или могут быть допустимы только в системе с резервированием типов, в зависимости от реализации.  
  
 Для поддержки практического использования `x:Members` как средства указания определений членов в разметке эти члены должны быть связаны с классом, который может быть изменен. Предполагаемая модель состоит в том, что `x:Members` существует в качестве члена типа, указывающего `x:Class`. Однако механизм для сопоставления типов и членов или для создания определений динамических членов не поддерживается на уровне служб XAML .NET Framework. Это отводится отдельным платформам, имеющим модели приложений, поддерживающие определения членов из XAML. Как правило, для поддержки этой функции требуются действия MSBUILD при построении, которые компилируют разметку XAML и либо интегрируют его с выделенным кодом, либо создают чистые сборки из XAML.  
  
## <a name="xproperty-for-windows-workflow-foundation"></a>x:Property для Windows Workflow Foundation  
 Для Windows Workflow Foundation `x:Property` определяет члены пользовательского действия, составленного полностью в XAML, или заданные XAML динамические члены для конструктора действий с выделенным кодом. `x:Class` также должен быть указан в корневом элементе рабочей среды XAML. Это не является обязательным на уровне служб XAML .NET Framework, но становится обязательным при загрузке рабочей среды XAML с помощью действий MSBUILD при построении, которые поддерживают пользовательские действия и Windows Workflow Foundation XAML в целом. Windows Workflow Foundation не использует чистое имя типа XAML в качестве его предполагаемого значения для `x:Property` `Type` атрибута, а вместо этого использует соглашение, которое не описаны ниже. Дополнительные сведения см. в разделе [Создание действия](http://msdn.microsoft.com/library/dd807392.aspx).

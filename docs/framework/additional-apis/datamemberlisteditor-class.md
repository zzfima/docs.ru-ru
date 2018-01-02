---
title: "Класс DataMemberListEditor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
api_name: System.Windows.Forms.Design.DataMemberListEditor
api_location: System.Design.dll
api_type: Assembly
ms.assetid: c11d5231-78f2-45a7-9210-3b2d0969370e
topic_type: apiref
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a630a7b09915ca7c6207d432c5e30530a2e1f004
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="datamemberlisteditor-class"></a><span data-ttu-id="40b8d-102">Класс DataMemberListEditor</span><span class="sxs-lookup"><span data-stu-id="40b8d-102">DataMemberListEditor Class</span></span>

<span data-ttu-id="40b8d-103">Предоставляет раскрывающийся список пользовательский интерфейс для редактирования свойств объектов с привязкой к данным (объекты, имеющие ненулевой `DataSource` свойства), перечисляя все свойства `DataSource` выберите источник значения из объекта.</span><span class="sxs-lookup"><span data-stu-id="40b8d-103">Provides a drop-down user interface for editing properties of data-bound objects (objects that have non-null `DataSource` property) by listing all properties of the `DataSource` object to select the value source from.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40b8d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40b8d-104">Syntax</span></span>
  
```csharp  
internal class DataMemberListEditor : UITypeEditor
```

> [!WARNING]
> <span data-ttu-id="40b8d-105">`DataMemberListEditor` Класса является внутренним и не предназначены для непосредственного использования в коде.</span><span class="sxs-lookup"><span data-stu-id="40b8d-105">The `DataMemberListEditor` class is internal and not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="40b8d-106">В реальном приложении ни при каких обстоятельствах корпорация Майкрософт не поддерживает использование этого класса.</span><span class="sxs-lookup"><span data-stu-id="40b8d-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="40b8d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="40b8d-107">Requirements</span></span>

<span data-ttu-id="40b8d-108">**Пространство имен:**<xref:System.Windows.Forms.Design?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="40b8d-108">**Namespace:** <xref:System.Windows.Forms.Design?displayProperty=nameWithType></span></span>  
  
<span data-ttu-id="40b8d-109">**Сборка:** System.Design (в System.Design.dll)</span><span class="sxs-lookup"><span data-stu-id="40b8d-109">**Assembly:** System.Design (in System.Design.dll)</span></span>  
  
<span data-ttu-id="40b8d-110">**Версии платформы .NET framework:** доступно с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="40b8d-110">**.NET Framework versions:** Available since 2.0.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40b8d-111">См. также</span><span class="sxs-lookup"><span data-stu-id="40b8d-111">See also</span></span>

<xref:System.Windows.Forms.Design?displayProperty=nameWithType>

---
title: Базовые действия в WF
ms.date: 03/30/2017
ms.assetid: 8e9009d1-236e-4d8e-86fc-e43132bf6dfc
ms.openlocfilehash: d87125d8d85fa33a49651dfabb840881b0e216ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="primitives-activities-in-wf"></a><span data-ttu-id="616c7-102">Базовые действия в WF</span><span class="sxs-lookup"><span data-stu-id="616c7-102">Primitives Activities in WF</span></span>
<span data-ttu-id="616c7-103">В [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] предусмотрено несколько предоставляемых системой действий, которые представляют собой удобный механизм выполнения общих задач.</span><span class="sxs-lookup"><span data-stu-id="616c7-103">[!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] provides several system-provided activities that provide a convenient mechanism for performing common tasks.</span></span>  
  
|<span data-ttu-id="616c7-104">Действие</span><span class="sxs-lookup"><span data-stu-id="616c7-104">Activity</span></span>|<span data-ttu-id="616c7-105">Описание</span><span class="sxs-lookup"><span data-stu-id="616c7-105">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.Assign>|<span data-ttu-id="616c7-106">Назначает значение переменной в текущей области.</span><span class="sxs-lookup"><span data-stu-id="616c7-106">Assigns a value to a variable at the current scope.</span></span>|  
|<xref:System.Activities.Statements.Delay>|<span data-ttu-id="616c7-107">Переводит один путь выполнения в состояние бездействия, что может позволить выгрузить рабочий процесс.</span><span class="sxs-lookup"><span data-stu-id="616c7-107">Puts one path of execution into an idle state, possibly allowing the workflow to be unloaded.</span></span>|  
|<xref:System.Activities.Statements.InvokeDelegate>|<span data-ttu-id="616c7-108">Выполняет делегат, который является производным от <xref:System.Activities.ActivityDelegate> и доступен как свойство.</span><span class="sxs-lookup"><span data-stu-id="616c7-108">Executes a delegate that derives from <xref:System.Activities.ActivityDelegate> and is exposed as a property.</span></span>|  
|<xref:System.Activities.Statements.InvokeMethod>|<span data-ttu-id="616c7-109">Выполняет открытый метод объекта CLR.</span><span class="sxs-lookup"><span data-stu-id="616c7-109">Executes a public method of a CLR object.</span></span>|  
|<xref:System.Activities.Statements.WriteLine>|<span data-ttu-id="616c7-110">Отображает указанную строку на консоли или записывает в указанный объект <xref:System.IO.TextWriter>.</span><span class="sxs-lookup"><span data-stu-id="616c7-110">Writes a specified string to the console or a specified <xref:System.IO.TextWriter> object.</span></span>|

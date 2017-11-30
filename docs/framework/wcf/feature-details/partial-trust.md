---
title: "Частичное доверие"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489b1587-9909-4d0e-8c1a-5e83c8f8292b
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f3febf1f3703377806493c8067b50c149bce0108
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="partial-trust"></a><span data-ttu-id="fdf94-102">Частичное доверие</span><span class="sxs-lookup"><span data-stu-id="fdf94-102">Partial Trust</span></span>
<span data-ttu-id="fdf94-103">Начиная с версии [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] частично доверенные вызывающие пользователи могут обращаться к открытым типам и методам, реализованным в классах <xref:System.ServiceModel>, <xref:System.Runtime.Serialization> и <xref:System.ServiceModel.Web>.</span><span class="sxs-lookup"><span data-stu-id="fdf94-103">Starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)], partially trusted callers can access public types and methods implemented in <xref:System.ServiceModel>, <xref:System.Runtime.Serialization>, and <xref:System.ServiceModel.Web>.</span></span> <span data-ttu-id="fdf94-104">В этом разделе описываются сценарии использования [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в частично доверенном приложении, а также ограниченное подмножество функциональных возможностей [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], доступных приложениям, работающим с ограниченными разрешениями управления доступом для кода (CAS).</span><span class="sxs-lookup"><span data-stu-id="fdf94-104">This section describes supported scenarios for using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] within a partially trusted application as well as the limited subset of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] functionality available to applications running with reduced code access security (CAS) permissions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdf94-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="fdf94-105">In This Section</span></span>  
 [<span data-ttu-id="fdf94-106">Поддерживаемые сценарии развертывания</span><span class="sxs-lookup"><span data-stu-id="fdf94-106">Supported Deployment Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)  
 <span data-ttu-id="fdf94-107">Описывает основные сценарии частичного доверия для запуска [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="fdf94-107">Describes the main partial trust scenarios for running [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="fdf94-108">Совместимость возможностей частичного доверия</span><span class="sxs-lookup"><span data-stu-id="fdf94-108">Partial Trust Feature Compatibility</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md)  
 <span data-ttu-id="fdf94-109">Описывает функции [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которые не могут использоваться с частичным доверием.</span><span class="sxs-lookup"><span data-stu-id="fdf94-109">Describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features that cannot be used with partial trust.</span></span>  
  
 [<span data-ttu-id="fdf94-110">Рекомендации по работе с частичным доверием</span><span class="sxs-lookup"><span data-stu-id="fdf94-110">Partial Trust Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)  
 <span data-ttu-id="fdf94-111">Содержит рекомендации по использованию [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в частично доверенных приложениях.</span><span class="sxs-lookup"><span data-stu-id="fdf94-111">Contains best practices for using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in partially trusted applications.</span></span>

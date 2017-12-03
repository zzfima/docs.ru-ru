---
title: '&lt;workflowIdle&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 66b2ff0db90a8126027eca976f73b3a8b554e3f4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowidlegt"></a>&lt;workflowIdle&gt;
Поведение службы, управляющее выгрузкой и сохранением простаивающих экземпляров рабочего процесса.  
  
\<система. ServiceModel >  
\<поведения >  
\<serviceBehaviors >  
\<поведение >  
\<workflowIdle >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|timeToPersist|Значение Timespan, которое указывает время между моментом рабочий процесс переходит в состояние бездействия и сохраняется. Значение по умолчанию — TimeSpan.MaxValue.<br /><br /> Начало интервала определяется моментом, когда экземпляр рабочего процесса становится неактивным. Этот атрибут полезен, если вы хотите сохранить экземпляр рабочего процесса активнее, при этом оставляя экземпляр в памяти в то же время. Этот атрибут действителен, только если его значение меньше, чем **timeToUnload** атрибута. Если значение больше, оно не учитывается. Если этот атрибут истекает до значения, указанного в **timeToUnload** атрибут, сохранение должно быть завершено до выгрузки рабочего процесса. Это означает, что операция выгрузки может быть задержана, пока рабочий процесс не будет сохранен. Уровень сохраняемости ответственен за обработку повторений для временных ошибок и выдает исключения только для неустранимых ошибок. В связи с этим все исключения, возникшие во время сохранения, считаются неустранимыми, и производится прерывание работы экземпляра рабочего процесса.|  
|timeToUnload|Значение Timespan, указывающее интервал времени от момента, когда рабочий процесс стал неактивным, до его выгрузки. Значение по умолчанию - 1 минута.<br /><br /> При выгрузке рабочего процесса подразумевается, что было произведено его сохранение. Если этот атрибут имеет значение ноль, экземпляр рабочего процесса сохраняется и выгружается сразу после рабочий процесс становится неактивным. Задав этому атрибуту значение TimeSpan.MaxValue фактически операция выгрузки будет отключена. Простаивающие экземпляры рабочего процесса не выгружаются.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение > из \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Указывает элемент поведения.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>

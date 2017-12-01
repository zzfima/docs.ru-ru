---
title: "Программируемость хранилища метаданных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3b38aec2e3f06e1f998bbc042c70909d208d3b63
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2017
---
# <a name="metadata-store-programmability"></a>Программируемость хранилища метаданных
Хранилище метаданных является компонентом [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)], позволяющим сопоставлять произвольные метаданные в форме атрибутов CLR с типами во время выполнения. Это предусматривает слабую связь между компонентами времени выполнения и их аналогами во время разработки, а также возможность изменять компоненты времени разработки, не влияя на время выполнения. Образец демонстрирует программирование хранилища метаданных путем применения атрибутов к типам времени выполнения, для которых отсутствует управление их источником. Обычно используется терминология, согласно которой ведущее приложение регистрирует метаданные для набора типов.  
  
 В выходных данных, вы можете заметить дополнительный непредвиденный атрибут, <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`. Он добавляется при использовании API-интерфейса метаданных и не влияет на выполнение образца.  
  
 В этом образце показаны следующие действия.  
  
## <a name="demonstrates"></a>Демонстрации  
  
-   Внедрение атрибута с использованием API хранилища метаданных.  
  
-   Использование механизма обратного вызова, чтобы отложить регистрацию метаданных.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения ProgrammingMetadataStore.sln.  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Чтобы запустить решение, нажмите клавишу F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`
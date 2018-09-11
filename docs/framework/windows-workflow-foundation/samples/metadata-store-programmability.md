---
title: Программируемость хранилища метаданных
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 4ea6117686b985a9ea18ce4e5cc4ea2b5c25524c
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44276332"
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
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`
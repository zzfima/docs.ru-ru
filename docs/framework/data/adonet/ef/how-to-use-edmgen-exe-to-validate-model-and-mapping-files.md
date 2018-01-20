---
title: "Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ae70c90fc20265334cdfb55e4a0f88724284d822
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Практическое руководство. Использование EdmGen.exe для проверки файлов модели и сопоставления
В этом разделе показано, как использовать [генератор модели EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) средством для проверки файлов модели и сопоставления. Дополнительные сведения см. в разделе [модели EDM](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Проверка модели School при помощи программы EdmGen.exe  
  
1.  Создайте базу данных School. Дополнительные сведения см. в разделе [Создание образца базы данных School](http://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Сформируйте модель School. Дополнительные сведения см. в разделе [как: использование EdmGen.exe для создания модели и сопоставления файлов](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>См. также  
 [Как: вручную настроить проект Entity Framework](http://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [Средства работы с моделью EDM ADO.NET](http://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [Как: заранее создать представления для повышения производительности запросов](http://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [Практическое руководство. Использование EdmGen.exe для создания кода объектного уровня](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)

---
title: Как выполнить  Использование EdmGen.exe для проверки файлов модели и сопоставления
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 12258236c904c70d6d94490e3d1c6af2457bbe0c
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/07/2019
ms.locfileid: "55827894"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Как выполнить  Использование EdmGen.exe для проверки файлов модели и сопоставления
В этом разделе показано, как использовать [генератор модели EDM (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) средство для проверки файлов модели и сопоставления. Дополнительные сведения см. в разделе [модели EDM](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Проверка модели School при помощи программы EdmGen.exe  
  
1.  Создайте базу данных School. Дополнительные сведения см. в разделе [Создание образца базы данных School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2.  Сформируйте модель School. Дополнительные сведения см. в разделе [Как Использование EdmGen.exe для создания файлов модели и сопоставления](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  Выполните в командной строке следующую команду (введя ее без разрывов строк):  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Вручную настроить проект Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Средства модели EDM ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Практическое руководство. Предварительное создание представлений для повышения производительности запросов](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Практическое руководство. Использование EdmGen.exe для создания кода уровня объекта](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)

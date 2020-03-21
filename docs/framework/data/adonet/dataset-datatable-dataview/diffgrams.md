---
title: DiffGrams
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: 2c521ef33c98234dac5f4b819a800cd524218462
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151160"
---
# <a name="diffgrams"></a>DiffGrams
DiffGram - это формат XML, определяющий текущую и первоначальную версию элементов данных. Набор данных <xref:System.Data.DataSet> использует формат DiffGram для загрузки и хранения своего содержимого, а также для сериализации содержимого перед отправкой его по сетевому подключению. <xref:System.Data.DataSet> Когда a написан как DiffGram, он заполняет DiffGram всей необходимой информацией для точного воссоздания <xref:System.Data.DataSet>содержимого, хотя и не схемы, включая значения столбца как из **исходной,** так и из **версий строки,** информацию об ошибке строки и порядок строки.  
  
 При отправке и получении набора данных <xref:System.Data.DataSet> из веб-службы XML формат DiffGram используется неявно. Кроме того, при загрузке <xref:System.Data.DataSet> содержимого от XML с помощью метода <xref:System.Data.DataSet> **ReadXml,** или при написании содержимого в XML с помощью метода **WriteXml,** можно указать, что содержимое будет прочитано или написано как DiffGram. Для получения дополнительной информации смотрите [Загрузка DataSet от XML](loading-a-dataset-from-xml.md) и [написание содержимого DataSet как XML Data.](writing-dataset-contents-as-xml-data.md)  
  
 Хотя формат DiffGram в основном используется платформой .NET Framework как формат сериализации для содержимого набора данных <xref:System.Data.DataSet>, его можно также применять для изменения данных в таблицах базы данных Microsoft SQL Server.  
  
 Диффграмма генерируется путем написания содержимого всех таблиц в ** \<элемент диффграммы>.**  
  
### <a name="to-generate-a-diffgram"></a>Создание Diffgram  
  
1. Создайте список корневых таблиц (таблиц, не имеющих родителей).  
  
2. Для каждой таблицы и ее потомков в списке запишите текущую версию всех строк в первом разделе Diffgram.  
  
3. Для каждой <xref:System.Data.DataSet>таблицы в , написать оригинальную версию всех строк, если таковые имеется, в ** \<до>** разделе Diffgram.  
  
4. Для строк с ошибками напишите содержимое ** \<ошибок** в разделе ошибок>разделе Diffgram.  
  
 Diffgram обрабатывается в последовательном порядке от начала XML-файла до его конца.  
  
### <a name="to-process-a-diffgram"></a>Обработка Diffgram  
  
1. Обработайте первый раздел Diffgram, содержащий текущую версию строк.  
  
2. Обработайте второй или ** \<предшествующий раздел>,** содержащий исходную версию строки измененных и удаленных строк.  
  
    > [!NOTE]
    > Если строка помечена как удаленная, то операция удаления может удалить потомков этой строки в зависимости от свойства `Cascade` текущего набора данных <xref:System.Data.DataSet>.  
  
3. Обработайте ** \<ошибки>** разделе. Установите сведения об ошибках для всех заданных строк и столбцов каждого элемента в этом разделе.  
  
> [!NOTE]
> Если в Diffgram задан режим <xref:System.Data.XmlWriteMode>, то содержимое целевого набора <xref:System.Data.DataSet> и исходного набора <xref:System.Data.DataSet> могут различаться.  
  
## <a name="diffgram-format"></a>Формат дельт  
 Формат DiffGram содержит три раздела: текущие данные, исходные данные и раздел ошибок, как показано в следующем примере.  
  
```xml  
<?xml version="1.0"?>  
<diffgr:diffgram
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"  
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1"  
         xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  
   <DataInstance>  
   </DataInstance>  
  
  <diffgr:before>  
  </diffgr:before>  
  
  <diffgr:errors>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
 Формат DiffGram состоит из следующих блоков данных:  
  
 **\<**  ***DataInstance***  **>**  
 Название этого элемента, ***DataInstance***, используется для целей объяснения в этой документации. Элемент ***DataInstance*** представляет <xref:System.Data.DataSet> или ряд <xref:System.Data.DataTable>. Вместо *DataInstance*, элемент будет содержать <xref:System.Data.DataSet> имя <xref:System.Data.DataTable>или . Этот блок формата DiffGram содержит текущие данные, независимо от изменений в этих данных. Элемент, или строка, который был изменен, отождествляется с **диффгрем:hasChanges** аннотация.  
  
 **\<diffgr:до>**  
 Этот блок формата DiffGram содержит первоначальную версию строки. Элементы этого блока сопоставляются с элементами блока ***DataInstance*** с помощью аннотации **diffgr:id.**  
  
 **\<diffgr:ошибки>**  
 Этот блок формата DiffGram содержит информацию об ошибках для определенной строки в блоке ***DataInstance.*** Элементы этого блока сопоставляются с элементами блока ***DataInstance*** с помощью аннотации **diffgr:id.**  
  
## <a name="diffgram-annotations"></a>Заметки дельт  
 В формате DiffGrams используется несколько заметок для связывания элементов из разных блоков DiffGram, представляющих разные версии строк или сведения об ошибках в <xref:System.Data.DataSet>.  
  
 В следующей таблице описаны аннотации DiffGram, которые определяются в урне пространства имен **DiffGram:schemas-microsoft-com:xml-diffgram-v1**.  
  
|Заметка|Описание|  
|----------------|-----------------|  
|**id**|Используется для сопряжения элементов в ** \<диффгре: до>** и **\<** **>** ** \<диффгр: ошибки>** блоки элементов в блоке ***DataInstance.*** Значения с **диффгрем:id** аннотация находятся в форме *«TableName» (RowIdentifier).* Например: `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Определяет, какой **\<** элемент из блока ***DataInstance*** **>** является родительским элементом текущего элемента. Значения с **диффгрем:аннотация parentId** находятся в форме *«TableName» (RowIdentifier).* Например: `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Определяет строку в **\<** блоке ***DataInstance*** **>** как модифицированную. Аннотация **hasChanges** может иметь одно из следующих двух значений:<br /><br /> **Вставлен**<br /> Идентифицирует **добавленную** строку.<br /><br /> **Изменения**<br /> Идентифицирует **измененную** строку, содержащую **исходную** версию строки в ** \<диффгре: до>** блок. Обратите внимание, что **удаленные** строки будут иметь **исходную** версию строки в ** \<диффгре:** до **\<**>блок, но не будет аннотированного элемента в блоке ***DataInstance.*** **>**|  
|**hasErrors**|Идентифицирует строку **\<** в блоке ***DataInstance*** **>** с **помощью RowError**. Элемент ошибки помещается в ** \<diffgr:ошибки>** блок.|  
|**Ошибка**|Содержит текст **RowError** для конкретного элемента в ** \<diffgr:errors>** блок.|  
  
 Набор данных <xref:System.Data.DataSet> содержит дополнительные заметки при считывании или записи содержимого в формате DiffGram. В следующей таблице описаны дополнительные аннотации, которые определяются в урне пространства **имен:schemas-microsoft-com:xml-msdata**.  
  
|Заметка|Описание|  
|----------------|-----------------|  
|**RowOrder**|Сохраняет порядок строк исходных данных и определяет индекс строки в конкретной таблице <xref:System.Data.DataTable>.|  
|**Скрытые**|Идентифицирует столбец как имеющий свойство **ColumnMapping,** установленное на **MappingType.Hidden**. Атрибут написан в формате **msdata: скрытое** *значение* *«ColumnName» (columnName)*«. Например: `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Обратите внимание, что скрытые столбцы записываются как атрибут DiffGram только если они содержат данные. В остальных случаях этот параметр игнорируется.|  
  
## <a name="sample-diffgram"></a>Образец DiffGram  
 Ниже показан пример формата DiffGram. На нем показан результат обновления строки в таблице перед фиксацией изменений. Строка с идентификатором пользователя «ALFKI» была изменена, но не обновлена. В результате, есть **текущий** ряд с **диффгрем:id** **\<** "Клиенты1" в блоке ***DataInstance,*** **>** и **оригинальный** ряд с **диффгрем:id** "Customers1" в ** \<диффгре: до>** блок. Строка с CustomerID "ANATR" включает в себя **RowError**, `diffgr:hasErrors="true"` так что он аннотирован с и есть соответствующий элемент в ** \<diffgr:ошибки>** блок.  
  
```xml  
<diffgr:diffgram xmlns:msdata="urn:schemas-microsoft-com:xml-msdata" xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
  <CustomerDataSet>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0" diffgr:hasChanges="modified">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>New Company</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers2" msdata:rowOrder="1" diffgram:hasErrors="true">  
      <CustomerID>ANATR</CustomerID>  
      <CompanyName>Ana Trujillo Emparedados y Helados</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers3" msdata:rowOrder="2">  
      <CustomerID>ANTON</CustomerID>  
      <CompanyName>Antonio Moreno Taquera</CompanyName>  
    </Customers>  
    <Customers diffgr:id="Customers4" msdata:rowOrder="3">  
      <CustomerID>AROUT</CustomerID>  
      <CompanyName>Around the Horn</CompanyName>  
    </Customers>  
  </CustomerDataSet>  
  <diffgr:before>  
    <Customers diffgr:id="Customers1" msdata:rowOrder="0">  
      <CustomerID>ALFKI</CustomerID>  
      <CompanyName>Alfreds Futterkiste</CompanyName>  
    </Customers>  
  </diffgr:before>  
  <diffgr:errors>  
    <Customers diffgr:id="Customers2" diffgr:Error="An optimistic concurrency violation has occurred for this row."/>  
  </diffgr:errors>  
</diffgr:diffgram>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Загрузка набора данных из XML](loading-a-dataset-from-xml.md)
- [Запись содержимого набора как данных XML](writing-dataset-contents-as-xml-data.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)

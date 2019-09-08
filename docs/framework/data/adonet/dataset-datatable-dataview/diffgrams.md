---
title: DiffGrams
ms.date: 03/30/2017
ms.assetid: 037f3991-7bbc-424b-b52e-8b03585d3e34
ms.openlocfilehash: dd70c8d238ba47744eec6ab4a4c6bc1e80a3d0b3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784654"
---
# <a name="diffgrams"></a>DiffGrams
DiffGram - это формат XML, определяющий текущую и первоначальную версию элементов данных. Набор данных <xref:System.Data.DataSet> использует формат DiffGram для загрузки и хранения своего содержимого, а также для сериализации содержимого перед отправкой его по сетевому подключению. Когда объект <xref:System.Data.DataSet> записывается как DiffGram, он заполняет DiffGram всеми необходимыми сведениями, чтобы правильно воссоздать содержимое, хотя это не схема, <xref:System.Data.DataSet>включая значения столбцов из **оригинала** и  **Текущие** версии строк, сведения об ошибках строк и порядок строк.  
  
 При отправке и получении набора данных <xref:System.Data.DataSet> из веб-службы XML формат DiffGram используется неявно. Кроме того, при загрузке <xref:System.Data.DataSet> содержимого из XML с помощью метода **ReadXml** или при записи содержимого <xref:System.Data.DataSet> в XML с помощью метода **WriteXml** можно указать, что содержимое считывается или записывается в виде DiffGram. Дополнительные сведения см. в статьях [Загрузка набора данных из XML](loading-a-dataset-from-xml.md) и [запись содержимого набора данных в виде XML-данных](writing-dataset-contents-as-xml-data.md).  
  
 Хотя формат DiffGram в основном используется платформой .NET Framework как формат сериализации для содержимого набора данных <xref:System.Data.DataSet>, его можно также применять для изменения данных в таблицах базы данных Microsoft SQL Server.  
  
 Объект DiffGram создается путем записи содержимого всех таблиц в  **\<элемент > DiffGram** .  
  
### <a name="to-generate-a-diffgram"></a>Создание Diffgram  
  
1. Создайте список корневых таблиц (таблиц, не имеющих родителей).  
  
2. Для каждой таблицы и ее потомков в списке запишите текущую версию всех строк в первом разделе Diffgram.  
  
3. Для каждой таблицы в <xref:System.Data.DataSet>запишите исходную версию всех строк, если таковые имеются,  **\<в разделе Before >** в DiffGram.  
  
4. Для строк, имеющих ошибки, запишите содержимое ошибки в  **\<разделе ошибки >** в DiffGram.  
  
 Diffgram обрабатывается в последовательном порядке от начала XML-файла до его конца.  
  
### <a name="to-process-a-diffgram"></a>Обработка Diffgram  
  
1. Обработайте первый раздел Diffgram, содержащий текущую версию строк.  
  
2. Обработайте второй раздел или  **\<> Before** , который содержит исходную версию строк измененных и удаленных строк.  
  
    > [!NOTE]
    > Если строка помечена как удаленная, то операция удаления может удалить потомков этой строки в зависимости от свойства `Cascade` текущего набора данных <xref:System.Data.DataSet>.  
  
3. Обработайте раздел  **ошибок>.\<** Установите сведения об ошибках для всех заданных строк и столбцов каждого элемента в этом разделе.  
  
> [!NOTE]
> Если в Diffgram задан режим <xref:System.Data.XmlWriteMode>, то содержимое целевого набора <xref:System.Data.DataSet> и исходного набора <xref:System.Data.DataSet> могут различаться.  
  
## <a name="diffgram-format"></a>Формат DiffGram  
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
 Имя этого элемента, ***instance***, используется для объяснения целей в этой документации. Элемент ***instance*** представляет <xref:System.Data.DataSet> строку <xref:System.Data.DataTable>типа или. Вместо *экземпляра*данных элемент будет содержать имя <xref:System.Data.DataSet> или. <xref:System.Data.DataTable> Этот блок формата DiffGram содержит текущие данные, независимо от изменений в этих данных. Элемент (или строка), который был изменен, определяется с помощью аннотации **diffgr: hasChanges** .  
  
 **\<diffgr:before>**  
 Этот блок формата DiffGram содержит первоначальную версию строки. Элементы в этом блоке сопоставляются с элементами в блоке ***instance*** с помощью аннотации **diffgr: ID** .  
  
 **\<diffgr: ошибки >**  
 Этот блок формата DiffGram содержит сведения об ошибке для определенной строки в блоке ***экземпляра*** данных. Элементы в этом блоке сопоставляются с элементами в блоке ***instance*** с помощью аннотации **diffgr: ID** .  
  
## <a name="diffgram-annotations"></a>Заметки DiffGram  
 В формате DiffGrams используется несколько заметок для связывания элементов из разных блоков DiffGram, представляющих разные версии строк или сведения об ошибках в <xref:System.Data.DataSet>.  
  
 В следующей таблице описаны аннотации DiffGram, которые определены в пространстве имен **urn: schemas-microsoft-com: XML-DiffGram-v1**.  
  
|Комментарий|Описание|  
|----------------|-----------------|  
|**id**|Используется для связывания элементов в  **\<diffgr: before >** **\<** и  **\<diffgr: Errors >** блокирует элементы в блоке ***instance*** **>** . Значения с заметкой **diffgr: ID** представлены в формате *[TableName] [ровидентифиер]* . Например, `<Customers diffgr:id="Customers1">`.|  
|**parentId**|Определяет, какой элемент из **\<** блока данных- ***экземпляра*** **>** является родительским элементом текущего элемента. Значения с аннотацией **diffgr: ParentID** находятся в формате *[TableName] [ровидентифиер]* . Например, `<Orders diffgr:parentId="Customers1">`.|  
|**hasChanges**|Определяет строку в блоке **\<** экземпляра типа « ***экземпляр*** **>** » как измененную. Аннотация **HasChanges** может иметь одно из следующих двух значений:<br /><br /> **inserted**<br /> Определяет **добавленную** строку.<br /><br /> **изменения**<br /> Определяет **измененную** строку, содержащую **исходную**  **\<** версию строки в блоке diffgr: before >. Обратите внимание, что **Deleted** строки будут иметь **исходного** версию строки в  **\<diffgr: перед >** блок, но не с заметками элемент в будет **\<** ***DataInstance*** **>** блока.|  
|**hasErrors**|Определяет строку в **\<** блоке ***instance*** **>** с помощью **роверрор**. Элемент Error помещается в  **\<блок diffgr: Errors >** .|  
|**Ошибка**|Содержит текст **роверрор** для определенного элемента в  **\<блоке diffgr: Errors >** .|  
  
 Набор данных <xref:System.Data.DataSet> содержит дополнительные заметки при считывании или записи содержимого в формате DiffGram. В следующей таблице описаны эти дополнительные аннотации, которые определены в пространстве имен **urn: schemas-microsoft-com: XML-msdata**.  
  
|Комментарий|Описание|  
|----------------|-----------------|  
|**ровордер**|Сохраняет порядок строк исходных данных и определяет индекс строки в конкретной таблице <xref:System.Data.DataTable>.|  
|**Служеб**|Определяет столбец как свойство **ColumnMapping** имеет значение **MappingType. Hidden**. Атрибут записывается в формате **msdata: Hidden** *[имя_столбца]* = "*value*". Например, `<Customers diffgr:id="Customers1" msdata:hiddenContactTitle="Owner">`.<br /><br /> Обратите внимание, что скрытые столбцы записываются как атрибут DiffGram только если они содержат данные. В противном случае они пропускаются.|  
  
## <a name="sample-diffgram"></a>Образец DiffGram  
 Ниже показан пример формата DiffGram. На нем показан результат обновления строки в таблице перед фиксацией изменений. Строка с идентификатором пользователя «ALFKI» была изменена, но не обновлена. В результате существует **Текущая** строка с **diffgr: ID** "Customers1 **\<** " в блоке ***экземпляра*** **>** данных и **Исходная** строка с **идентификатором diffgr: ID** "Customers1" в  **\< diffgr: перед** блоком >. Строка с идентификатором CustomerID "анатр" включает **роверрор**, поэтому она снабжена заметками `diffgr:hasErrors="true"` и в блоке  **\<diffgr: Errors >** содержится связанный элемент.  
  
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
  
## <a name="see-also"></a>См. также

- [Использование XML в наборах данных](using-xml-in-a-dataset.md)
- [Загрузка DataSet из XML](loading-a-dataset-from-xml.md)
- [Запись содержимого DataSet как данных XML](writing-dataset-contents-as-xml-data.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)

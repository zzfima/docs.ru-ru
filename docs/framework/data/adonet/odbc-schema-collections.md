---
title: Коллекции схемы ODBC
ms.date: 03/30/2017
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
ms.openlocfilehash: 072a9cd365031cd5660d1824bc229d459abc5af8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525837"
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="c299a-102">Коллекции схемы ODBC</span><span class="sxs-lookup"><span data-stu-id="c299a-102">ODBC Schema Collections</span></span>
<span data-ttu-id="c299a-103">В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="c299a-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="c299a-104">Драйвер ODBC для Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="c299a-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="c299a-105">Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="c299a-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="c299a-106">Таблицы</span><span class="sxs-lookup"><span data-stu-id="c299a-106">Tables</span></span>  
  
-   <span data-ttu-id="c299a-107">Indexes</span><span class="sxs-lookup"><span data-stu-id="c299a-107">Indexes</span></span>  
  
-   <span data-ttu-id="c299a-108">Столбцы</span><span class="sxs-lookup"><span data-stu-id="c299a-108">Columns</span></span>  
  
-   <span data-ttu-id="c299a-109">Процедуры</span><span class="sxs-lookup"><span data-stu-id="c299a-109">Procedures</span></span>  
  
-   <span data-ttu-id="c299a-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c299a-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="c299a-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c299a-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="c299a-112">Представления</span><span class="sxs-lookup"><span data-stu-id="c299a-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="c299a-113">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="c299a-113">Tables and Views</span></span>  
  
|<span data-ttu-id="c299a-114">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-114">ColumnName</span></span>|<span data-ttu-id="c299a-115">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="c299a-116">TABLE_CAT</span></span>|<span data-ttu-id="c299a-117">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-117">String</span></span>|  
|<span data-ttu-id="c299a-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c299a-118">TABLE_SCHEM</span></span>|<span data-ttu-id="c299a-119">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-119">String</span></span>|  
|<span data-ttu-id="c299a-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-120">TABLE_NAME</span></span>|<span data-ttu-id="c299a-121">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-121">String</span></span>|  
|<span data-ttu-id="c299a-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-122">TABLE_TYPE</span></span>|<span data-ttu-id="c299a-123">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-123">String</span></span>|  
|<span data-ttu-id="c299a-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-124">REMARKS</span></span>|<span data-ttu-id="c299a-125">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="c299a-126">Indexes</span><span class="sxs-lookup"><span data-stu-id="c299a-126">Indexes</span></span>  
  
|<span data-ttu-id="c299a-127">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-127">ColumnName</span></span>|<span data-ttu-id="c299a-128">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="c299a-129">TABLE_CAT</span></span>|<span data-ttu-id="c299a-130">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-130">String</span></span>|  
|<span data-ttu-id="c299a-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c299a-131">TABLE_SCHEM</span></span>|<span data-ttu-id="c299a-132">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-132">String</span></span>|  
|<span data-ttu-id="c299a-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-133">TABLE_NAME</span></span>|<span data-ttu-id="c299a-134">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-134">String</span></span>|  
|<span data-ttu-id="c299a-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="c299a-135">NON_UNIQUE</span></span>|<span data-ttu-id="c299a-136">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-136">Int16</span></span>|  
|<span data-ttu-id="c299a-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c299a-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="c299a-138">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-138">String</span></span>|  
|<span data-ttu-id="c299a-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-139">INDEX_NAME</span></span>|<span data-ttu-id="c299a-140">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-140">String</span></span>|  
|<span data-ttu-id="c299a-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-141">TYPE</span></span>|<span data-ttu-id="c299a-142">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-142">Int16</span></span>|  
|<span data-ttu-id="c299a-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c299a-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="c299a-144">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-144">Int16</span></span>|  
|<span data-ttu-id="c299a-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-145">COLUMN_NAME</span></span>|<span data-ttu-id="c299a-146">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-146">String</span></span>|  
|<span data-ttu-id="c299a-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="c299a-147">ASC_OR_DESC</span></span>|<span data-ttu-id="c299a-148">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-148">String</span></span>|  
|<span data-ttu-id="c299a-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="c299a-149">CARDINATLITY</span></span>|<span data-ttu-id="c299a-150">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-150">Int32</span></span>|  
|<span data-ttu-id="c299a-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="c299a-151">PAGES</span></span>|<span data-ttu-id="c299a-152">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-152">Int32</span></span>|  
|<span data-ttu-id="c299a-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="c299a-153">FILTER_CONDITION</span></span>|<span data-ttu-id="c299a-154">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-154">String</span></span>|  
|<span data-ttu-id="c299a-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c299a-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c299a-156">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-156">String</span></span>|  
|<span data-ttu-id="c299a-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="c299a-158">Byte</span><span class="sxs-lookup"><span data-stu-id="c299a-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c299a-159">Столбцы</span><span class="sxs-lookup"><span data-stu-id="c299a-159">Columns</span></span>  
  
|<span data-ttu-id="c299a-160">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-160">ColumnName</span></span>|<span data-ttu-id="c299a-161">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="c299a-162">TABLE_CAT</span></span>|<span data-ttu-id="c299a-163">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-163">String</span></span>|  
|<span data-ttu-id="c299a-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c299a-164">TABLE_SCHEM</span></span>|<span data-ttu-id="c299a-165">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-165">String</span></span>|  
|<span data-ttu-id="c299a-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-166">TABLE_NAME</span></span>|<span data-ttu-id="c299a-167">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-167">String</span></span>|  
|<span data-ttu-id="c299a-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-168">COLUMN_NAME</span></span>|<span data-ttu-id="c299a-169">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-169">String</span></span>|  
|<span data-ttu-id="c299a-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-170">DATA_TYPE</span></span>|<span data-ttu-id="c299a-171">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-171">Int16</span></span>|  
|<span data-ttu-id="c299a-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-172">TYPE_NAME</span></span>|<span data-ttu-id="c299a-173">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-173">String</span></span>|  
|<span data-ttu-id="c299a-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c299a-174">COLUMN_SIZE</span></span>|<span data-ttu-id="c299a-175">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-175">Int32</span></span>|  
|<span data-ttu-id="c299a-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="c299a-177">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-177">Int32</span></span>|  
|<span data-ttu-id="c299a-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c299a-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c299a-179">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-179">Int16</span></span>|  
|<span data-ttu-id="c299a-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c299a-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c299a-181">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-181">Int16</span></span>|  
|<span data-ttu-id="c299a-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-182">NULLABLE</span></span>|<span data-ttu-id="c299a-183">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-183">Int16</span></span>|  
|<span data-ttu-id="c299a-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-184">REMARKS</span></span>|<span data-ttu-id="c299a-185">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-185">String</span></span>|  
|<span data-ttu-id="c299a-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c299a-186">COLUMN_DEF</span></span>|<span data-ttu-id="c299a-187">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-187">String</span></span>|  
|<span data-ttu-id="c299a-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c299a-189">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-189">Int16</span></span>|  
|<span data-ttu-id="c299a-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c299a-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c299a-191">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-191">Int16</span></span>|  
|<span data-ttu-id="c299a-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c299a-193">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-193">Int32</span></span>|  
|<span data-ttu-id="c299a-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c299a-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="c299a-195">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-195">Int32</span></span>|  
|<span data-ttu-id="c299a-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-196">IS_NULLABLE</span></span>|<span data-ttu-id="c299a-197">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-197">String</span></span>|  
|<span data-ttu-id="c299a-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c299a-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="c299a-199">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-199">String</span></span>|  
|<span data-ttu-id="c299a-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c299a-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c299a-201">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-201">String</span></span>|  
|<span data-ttu-id="c299a-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="c299a-203">Byte</span><span class="sxs-lookup"><span data-stu-id="c299a-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c299a-204">Процедуры</span><span class="sxs-lookup"><span data-stu-id="c299a-204">Procedures</span></span>  
  
|<span data-ttu-id="c299a-205">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-205">ColumnName</span></span>|<span data-ttu-id="c299a-206">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c299a-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="c299a-208">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-208">String</span></span>|  
|<span data-ttu-id="c299a-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c299a-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c299a-210">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-210">String</span></span>|  
|<span data-ttu-id="c299a-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="c299a-212">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-212">String</span></span>|  
|<span data-ttu-id="c299a-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c299a-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="c299a-214">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-214">Int32</span></span>|  
|<span data-ttu-id="c299a-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c299a-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="c299a-216">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-216">Int32</span></span>|  
|<span data-ttu-id="c299a-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="c299a-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="c299a-218">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-218">Int32</span></span>|  
|<span data-ttu-id="c299a-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-219">REMARKS</span></span>|<span data-ttu-id="c299a-220">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-220">String</span></span>|  
|<span data-ttu-id="c299a-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c299a-222">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="c299a-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c299a-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="c299a-224">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-224">ColumnName</span></span>|<span data-ttu-id="c299a-225">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c299a-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="c299a-227">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-227">String</span></span>|  
|<span data-ttu-id="c299a-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c299a-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c299a-229">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-229">String</span></span>|  
|<span data-ttu-id="c299a-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="c299a-231">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-231">String</span></span>|  
|<span data-ttu-id="c299a-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-232">COLUMN_NAME</span></span>|<span data-ttu-id="c299a-233">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-233">String</span></span>|  
|<span data-ttu-id="c299a-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-234">COLUMN_TYPE</span></span>|<span data-ttu-id="c299a-235">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-235">Int16</span></span>|  
|<span data-ttu-id="c299a-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-236">DATA_TYPE</span></span>|<span data-ttu-id="c299a-237">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-237">Int16</span></span>|  
|<span data-ttu-id="c299a-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-238">TYPE_NAME</span></span>|<span data-ttu-id="c299a-239">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-239">String</span></span>|  
|<span data-ttu-id="c299a-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c299a-240">COLUMN_SIZE</span></span>|<span data-ttu-id="c299a-241">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-241">Int32</span></span>|  
|<span data-ttu-id="c299a-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="c299a-243">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-243">Int32</span></span>|  
|<span data-ttu-id="c299a-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c299a-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c299a-245">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-245">Int16</span></span>|  
|<span data-ttu-id="c299a-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c299a-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c299a-247">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-247">Int16</span></span>|  
|<span data-ttu-id="c299a-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-248">NULLABLE</span></span>|<span data-ttu-id="c299a-249">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-249">Int16</span></span>|  
|<span data-ttu-id="c299a-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-250">REMARKS</span></span>|<span data-ttu-id="c299a-251">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-251">String</span></span>|  
|<span data-ttu-id="c299a-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c299a-252">COLUMN_DEF</span></span>|<span data-ttu-id="c299a-253">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-253">String</span></span>|  
|<span data-ttu-id="c299a-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c299a-255">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-255">Int16</span></span>|  
|<span data-ttu-id="c299a-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c299a-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c299a-257">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-257">Int16</span></span>|  
|<span data-ttu-id="c299a-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c299a-259">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-259">Int32</span></span>|  
|<span data-ttu-id="c299a-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c299a-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="c299a-261">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-261">Int32</span></span>|  
|<span data-ttu-id="c299a-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-262">IS_NULLABLE</span></span>|<span data-ttu-id="c299a-263">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-263">String</span></span>|  
|<span data-ttu-id="c299a-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c299a-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="c299a-265">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-265">String</span></span>|  
|<span data-ttu-id="c299a-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c299a-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c299a-267">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-267">String</span></span>|  
|<span data-ttu-id="c299a-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="c299a-269">Byte</span><span class="sxs-lookup"><span data-stu-id="c299a-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="c299a-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c299a-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="c299a-271">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-271">ColumnName</span></span>|<span data-ttu-id="c299a-272">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c299a-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="c299a-274">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-274">String</span></span>|  
|<span data-ttu-id="c299a-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c299a-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c299a-276">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-276">String</span></span>|  
|<span data-ttu-id="c299a-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="c299a-278">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-278">String</span></span>|  
|<span data-ttu-id="c299a-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-279">COLUMN_NAME</span></span>|<span data-ttu-id="c299a-280">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-280">String</span></span>|  
|<span data-ttu-id="c299a-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-281">COLUMN_TYPE</span></span>|<span data-ttu-id="c299a-282">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-282">Int16</span></span>|  
|<span data-ttu-id="c299a-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-283">DATA_TYPE</span></span>|<span data-ttu-id="c299a-284">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-284">Int16</span></span>|  
|<span data-ttu-id="c299a-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-285">TYPE_NAME</span></span>|<span data-ttu-id="c299a-286">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-286">String</span></span>|  
|<span data-ttu-id="c299a-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c299a-287">COLUMN_SIZE</span></span>|<span data-ttu-id="c299a-288">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-288">Int32</span></span>|  
|<span data-ttu-id="c299a-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="c299a-290">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-290">Int32</span></span>|  
|<span data-ttu-id="c299a-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c299a-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c299a-292">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-292">Int16</span></span>|  
|<span data-ttu-id="c299a-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c299a-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c299a-294">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-294">Int16</span></span>|  
|<span data-ttu-id="c299a-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-295">NULLABLE</span></span>|<span data-ttu-id="c299a-296">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-296">Int16</span></span>|  
|<span data-ttu-id="c299a-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-297">REMARKS</span></span>|<span data-ttu-id="c299a-298">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-298">String</span></span>|  
|<span data-ttu-id="c299a-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c299a-299">COLUMN_DEF</span></span>|<span data-ttu-id="c299a-300">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-300">String</span></span>|  
|<span data-ttu-id="c299a-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c299a-302">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-302">Int16</span></span>|  
|<span data-ttu-id="c299a-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c299a-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c299a-304">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-304">Int16</span></span>|  
|<span data-ttu-id="c299a-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c299a-306">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-306">Int32</span></span>|  
|<span data-ttu-id="c299a-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c299a-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="c299a-308">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-308">Int32</span></span>|  
|<span data-ttu-id="c299a-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-309">IS_NULLABLE</span></span>|<span data-ttu-id="c299a-310">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-310">String</span></span>|  
|<span data-ttu-id="c299a-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="c299a-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="c299a-312">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-312">String</span></span>|  
|<span data-ttu-id="c299a-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="c299a-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="c299a-314">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-314">String</span></span>|  
|<span data-ttu-id="c299a-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="c299a-316">Byte</span><span class="sxs-lookup"><span data-stu-id="c299a-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="c299a-317">Драйвер ODBC для Oracle (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c299a-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="c299a-318">Microsoft SQL Server драйвер ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="c299a-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="c299a-319">Таблицы</span><span class="sxs-lookup"><span data-stu-id="c299a-319">Tables</span></span>  
  
-   <span data-ttu-id="c299a-320">Столбцы</span><span class="sxs-lookup"><span data-stu-id="c299a-320">Columns</span></span>  
  
-   <span data-ttu-id="c299a-321">Процедуры</span><span class="sxs-lookup"><span data-stu-id="c299a-321">Procedures</span></span>  
  
-   <span data-ttu-id="c299a-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c299a-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="c299a-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c299a-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="c299a-324">Представления</span><span class="sxs-lookup"><span data-stu-id="c299a-324">Views</span></span>  
  
-   <span data-ttu-id="c299a-325">Indexes</span><span class="sxs-lookup"><span data-stu-id="c299a-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="c299a-326">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="c299a-326">Tables and Views</span></span>  
  
|<span data-ttu-id="c299a-327">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-327">ColumnName</span></span>|<span data-ttu-id="c299a-328">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c299a-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c299a-330">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-330">String</span></span>|  
|<span data-ttu-id="c299a-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c299a-331">TABLE_OWNER</span></span>|<span data-ttu-id="c299a-332">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-332">String</span></span>|  
|<span data-ttu-id="c299a-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-333">TABLE_NAME</span></span>|<span data-ttu-id="c299a-334">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-334">String</span></span>|  
|<span data-ttu-id="c299a-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-335">TABLE_TYPE</span></span>|<span data-ttu-id="c299a-336">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-336">String</span></span>|  
|<span data-ttu-id="c299a-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-337">REMARKS</span></span>|<span data-ttu-id="c299a-338">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c299a-339">Столбцы</span><span class="sxs-lookup"><span data-stu-id="c299a-339">Columns</span></span>  
  
|<span data-ttu-id="c299a-340">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-340">ColumnName</span></span>|<span data-ttu-id="c299a-341">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c299a-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c299a-343">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-343">String</span></span>|  
|<span data-ttu-id="c299a-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c299a-344">TABLE_OWNER</span></span>|<span data-ttu-id="c299a-345">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-345">String</span></span>|  
|<span data-ttu-id="c299a-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-346">TABLE_NAME</span></span>|<span data-ttu-id="c299a-347">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-347">String</span></span>|  
|<span data-ttu-id="c299a-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-348">COLUMN_NAME</span></span>|<span data-ttu-id="c299a-349">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-349">String</span></span>|  
|<span data-ttu-id="c299a-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-350">DATA_TYPE</span></span>|<span data-ttu-id="c299a-351">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-351">Int16</span></span>|  
|<span data-ttu-id="c299a-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-352">TYPE_NAME</span></span>|<span data-ttu-id="c299a-353">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-353">String</span></span>|  
|<span data-ttu-id="c299a-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c299a-354">PRECISION</span></span>|<span data-ttu-id="c299a-355">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-355">Int32</span></span>|  
|<span data-ttu-id="c299a-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-356">LENGTH</span></span>|<span data-ttu-id="c299a-357">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-357">Int32</span></span>|  
|<span data-ttu-id="c299a-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="c299a-358">SCALE</span></span>|<span data-ttu-id="c299a-359">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-359">Int16</span></span>|  
|<span data-ttu-id="c299a-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="c299a-360">RADIX</span></span>|<span data-ttu-id="c299a-361">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-361">Int16</span></span>|  
|<span data-ttu-id="c299a-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-362">NULLABLE</span></span>|<span data-ttu-id="c299a-363">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-363">Int16</span></span>|  
|<span data-ttu-id="c299a-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-364">REMARKS</span></span>|<span data-ttu-id="c299a-365">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-365">String</span></span>|  
|<span data-ttu-id="c299a-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c299a-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="c299a-367">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c299a-368">Процедуры</span><span class="sxs-lookup"><span data-stu-id="c299a-368">Procedures</span></span>  
  
|<span data-ttu-id="c299a-369">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-369">ColumnName</span></span>|<span data-ttu-id="c299a-370">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c299a-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c299a-372">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-372">String</span></span>|  
|<span data-ttu-id="c299a-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c299a-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c299a-374">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-374">String</span></span>|  
|<span data-ttu-id="c299a-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="c299a-376">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-376">String</span></span>|  
|<span data-ttu-id="c299a-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c299a-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="c299a-378">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-378">Int16</span></span>|  
|<span data-ttu-id="c299a-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c299a-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="c299a-380">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-380">Int16</span></span>|  
|<span data-ttu-id="c299a-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="c299a-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="c299a-382">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-382">Int16</span></span>|  
|<span data-ttu-id="c299a-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-383">REMARKS</span></span>|<span data-ttu-id="c299a-384">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-384">String</span></span>|  
|<span data-ttu-id="c299a-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c299a-386">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="c299a-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c299a-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="c299a-388">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-388">ColumnName</span></span>|<span data-ttu-id="c299a-389">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c299a-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c299a-391">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-391">String</span></span>|  
|<span data-ttu-id="c299a-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c299a-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c299a-393">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-393">String</span></span>|  
|<span data-ttu-id="c299a-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="c299a-395">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-395">String</span></span>|  
|<span data-ttu-id="c299a-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-396">COLUMN_NAME</span></span>|<span data-ttu-id="c299a-397">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-397">String</span></span>|  
|<span data-ttu-id="c299a-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-398">COLUMN_TYPE</span></span>|<span data-ttu-id="c299a-399">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-399">Int16</span></span>|  
|<span data-ttu-id="c299a-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-400">DATA_TYPE</span></span>|<span data-ttu-id="c299a-401">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-401">Int16</span></span>|  
|<span data-ttu-id="c299a-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-402">TYPE_NAME</span></span>|<span data-ttu-id="c299a-403">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-403">String</span></span>|  
|<span data-ttu-id="c299a-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c299a-404">PRECISION</span></span>|<span data-ttu-id="c299a-405">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-405">Int32</span></span>|  
|<span data-ttu-id="c299a-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-406">LENGTH</span></span>|<span data-ttu-id="c299a-407">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-407">Int32</span></span>|  
|<span data-ttu-id="c299a-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="c299a-408">SCALE</span></span>|<span data-ttu-id="c299a-409">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-409">Int16</span></span>|  
|<span data-ttu-id="c299a-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="c299a-410">RADIX</span></span>|<span data-ttu-id="c299a-411">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-411">Int16</span></span>|  
|<span data-ttu-id="c299a-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-412">NULLABLE</span></span>|<span data-ttu-id="c299a-413">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-413">Int16</span></span>|  
|<span data-ttu-id="c299a-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-414">REMARKS</span></span>|<span data-ttu-id="c299a-415">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-415">String</span></span>|  
|<span data-ttu-id="c299a-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="c299a-416">OVERLOAD</span></span>|<span data-ttu-id="c299a-417">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-417">Int32</span></span>|  
|<span data-ttu-id="c299a-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c299a-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="c299a-419">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="c299a-420">Драйвер ODBC для Jet (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="c299a-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="c299a-421">Драйвер ODBC для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.</span><span class="sxs-lookup"><span data-stu-id="c299a-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="c299a-422">Таблицы</span><span class="sxs-lookup"><span data-stu-id="c299a-422">Tables</span></span>  
  
-   <span data-ttu-id="c299a-423">Indexes</span><span class="sxs-lookup"><span data-stu-id="c299a-423">Indexes</span></span>  
  
-   <span data-ttu-id="c299a-424">Столбцы</span><span class="sxs-lookup"><span data-stu-id="c299a-424">Columns</span></span>  
  
-   <span data-ttu-id="c299a-425">Процедуры</span><span class="sxs-lookup"><span data-stu-id="c299a-425">Procedures</span></span>  
  
-   <span data-ttu-id="c299a-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c299a-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="c299a-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c299a-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="c299a-428">Представления</span><span class="sxs-lookup"><span data-stu-id="c299a-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="c299a-429">Tables и Views</span><span class="sxs-lookup"><span data-stu-id="c299a-429">Tables and Views</span></span>  
  
|<span data-ttu-id="c299a-430">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-430">ColumnName</span></span>|<span data-ttu-id="c299a-431">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c299a-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c299a-433">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-433">String</span></span>|  
|<span data-ttu-id="c299a-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c299a-434">TABLE_OWNER</span></span>|<span data-ttu-id="c299a-435">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-435">String</span></span>|  
|<span data-ttu-id="c299a-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-436">TABLE_NAME</span></span>|<span data-ttu-id="c299a-437">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-437">String</span></span>|  
|<span data-ttu-id="c299a-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-438">TABLE_TYPE</span></span>|<span data-ttu-id="c299a-439">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-439">String</span></span>|  
|<span data-ttu-id="c299a-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-440">REMARKS</span></span>|<span data-ttu-id="c299a-441">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="c299a-442">Столбцы</span><span class="sxs-lookup"><span data-stu-id="c299a-442">Columns</span></span>  
  
|<span data-ttu-id="c299a-443">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-443">ColumnName</span></span>|<span data-ttu-id="c299a-444">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c299a-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="c299a-446">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-446">String</span></span>|  
|<span data-ttu-id="c299a-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c299a-447">TABLE_OWNER</span></span>|<span data-ttu-id="c299a-448">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-448">String</span></span>|  
|<span data-ttu-id="c299a-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-449">TABLE_NAME</span></span>|<span data-ttu-id="c299a-450">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-450">String</span></span>|  
|<span data-ttu-id="c299a-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-451">COLUMN_NAME</span></span>|<span data-ttu-id="c299a-452">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-452">String</span></span>|  
|<span data-ttu-id="c299a-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-453">DATA_TYPE</span></span>|<span data-ttu-id="c299a-454">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-454">Int16</span></span>|  
|<span data-ttu-id="c299a-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-455">TYPE_NAME</span></span>|<span data-ttu-id="c299a-456">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-456">String</span></span>|  
|<span data-ttu-id="c299a-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c299a-457">PRECISION</span></span>|<span data-ttu-id="c299a-458">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-458">Int32</span></span>|  
|<span data-ttu-id="c299a-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-459">LENGTH</span></span>|<span data-ttu-id="c299a-460">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-460">Int32</span></span>|  
|<span data-ttu-id="c299a-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="c299a-461">SCALE</span></span>|<span data-ttu-id="c299a-462">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-462">Int16</span></span>|  
|<span data-ttu-id="c299a-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="c299a-463">RADIX</span></span>|<span data-ttu-id="c299a-464">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-464">Int16</span></span>|  
|<span data-ttu-id="c299a-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-465">NULLABLE</span></span>|<span data-ttu-id="c299a-466">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-466">Int16</span></span>|  
|<span data-ttu-id="c299a-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-467">REMARKS</span></span>|<span data-ttu-id="c299a-468">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-468">String</span></span>|  
|<span data-ttu-id="c299a-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c299a-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="c299a-470">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="c299a-471">Процедуры</span><span class="sxs-lookup"><span data-stu-id="c299a-471">Procedures</span></span>  
  
|<span data-ttu-id="c299a-472">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-472">ColumnName</span></span>|<span data-ttu-id="c299a-473">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c299a-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c299a-475">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-475">String</span></span>|  
|<span data-ttu-id="c299a-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c299a-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c299a-477">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-477">String</span></span>|  
|<span data-ttu-id="c299a-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="c299a-479">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-479">String</span></span>|  
|<span data-ttu-id="c299a-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c299a-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="c299a-481">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-481">Int16</span></span>|  
|<span data-ttu-id="c299a-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="c299a-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="c299a-483">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-483">Int16</span></span>|  
|<span data-ttu-id="c299a-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="c299a-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="c299a-485">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-485">Int16</span></span>|  
|<span data-ttu-id="c299a-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-486">REMARKS</span></span>|<span data-ttu-id="c299a-487">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-487">String</span></span>|  
|<span data-ttu-id="c299a-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="c299a-489">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="c299a-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="c299a-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="c299a-491">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-491">ColumnName</span></span>|<span data-ttu-id="c299a-492">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="c299a-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="c299a-494">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-494">String</span></span>|  
|<span data-ttu-id="c299a-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="c299a-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="c299a-496">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-496">String</span></span>|  
|<span data-ttu-id="c299a-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="c299a-498">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-498">String</span></span>|  
|<span data-ttu-id="c299a-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-499">COLUMN_NAME</span></span>|<span data-ttu-id="c299a-500">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-500">String</span></span>|  
|<span data-ttu-id="c299a-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-501">COLUMN_TYPE</span></span>|<span data-ttu-id="c299a-502">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-502">Int16</span></span>|  
|<span data-ttu-id="c299a-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-503">DATA_TYPE</span></span>|<span data-ttu-id="c299a-504">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-504">Int16</span></span>|  
|<span data-ttu-id="c299a-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-505">TYPE_NAME</span></span>|<span data-ttu-id="c299a-506">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-506">String</span></span>|  
|<span data-ttu-id="c299a-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="c299a-507">PRECISION</span></span>|<span data-ttu-id="c299a-508">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-508">Int32</span></span>|  
|<span data-ttu-id="c299a-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-509">LENGTH</span></span>|<span data-ttu-id="c299a-510">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-510">Int32</span></span>|  
|<span data-ttu-id="c299a-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="c299a-511">SCALE</span></span>|<span data-ttu-id="c299a-512">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-512">Int16</span></span>|  
|<span data-ttu-id="c299a-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="c299a-513">RADIX</span></span>|<span data-ttu-id="c299a-514">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-514">Int16</span></span>|  
|<span data-ttu-id="c299a-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-515">NULLABLE</span></span>|<span data-ttu-id="c299a-516">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-516">Int16</span></span>|  
|<span data-ttu-id="c299a-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-517">REMARKS</span></span>|<span data-ttu-id="c299a-518">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-518">String</span></span>|  
|<span data-ttu-id="c299a-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="c299a-519">OVERLOAD</span></span>|<span data-ttu-id="c299a-520">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-520">Int32</span></span>|  
|<span data-ttu-id="c299a-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c299a-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="c299a-522">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="c299a-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="c299a-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="c299a-524">ColumnName</span><span class="sxs-lookup"><span data-stu-id="c299a-524">ColumnName</span></span>|<span data-ttu-id="c299a-525">DataType</span><span class="sxs-lookup"><span data-stu-id="c299a-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c299a-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="c299a-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="c299a-527">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-527">String</span></span>|  
|<span data-ttu-id="c299a-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="c299a-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="c299a-529">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-529">String</span></span>|  
|<span data-ttu-id="c299a-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="c299a-531">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-531">String</span></span>|  
|<span data-ttu-id="c299a-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-532">COLUMN_NAME</span></span>|<span data-ttu-id="c299a-533">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-533">String</span></span>|  
|<span data-ttu-id="c299a-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-534">COLUMN_TYPE</span></span>|<span data-ttu-id="c299a-535">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-535">Int16</span></span>|  
|<span data-ttu-id="c299a-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-536">DATA_TYPE</span></span>|<span data-ttu-id="c299a-537">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-537">Int16</span></span>|  
|<span data-ttu-id="c299a-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="c299a-538">TYPE_NAME</span></span>|<span data-ttu-id="c299a-539">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-539">String</span></span>|  
|<span data-ttu-id="c299a-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="c299a-540">COLUMN_SIZE</span></span>|<span data-ttu-id="c299a-541">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-541">Int32</span></span>|  
|<span data-ttu-id="c299a-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="c299a-543">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-543">Int32</span></span>|  
|<span data-ttu-id="c299a-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="c299a-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="c299a-545">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-545">Int16</span></span>|  
|<span data-ttu-id="c299a-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="c299a-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="c299a-547">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-547">Int16</span></span>|  
|<span data-ttu-id="c299a-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-548">NULLABLE</span></span>|<span data-ttu-id="c299a-549">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-549">Int16</span></span>|  
|<span data-ttu-id="c299a-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="c299a-550">REMARKS</span></span>|<span data-ttu-id="c299a-551">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-551">String</span></span>|  
|<span data-ttu-id="c299a-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="c299a-552">COLUMN_DEF</span></span>|<span data-ttu-id="c299a-553">Строковое</span><span class="sxs-lookup"><span data-stu-id="c299a-553">String</span></span>|  
|<span data-ttu-id="c299a-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="c299a-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="c299a-555">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-555">Int16</span></span>|  
|<span data-ttu-id="c299a-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="c299a-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="c299a-557">Int16</span><span class="sxs-lookup"><span data-stu-id="c299a-557">Int16</span></span>|  
|<span data-ttu-id="c299a-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="c299a-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="c299a-559">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-559">Int32</span></span>|  
|<span data-ttu-id="c299a-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="c299a-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="c299a-561">Int32</span><span class="sxs-lookup"><span data-stu-id="c299a-561">Int32</span></span>|  
|<span data-ttu-id="c299a-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="c299a-562">IS_NULLABLE</span></span>|<span data-ttu-id="c299a-563">String</span><span class="sxs-lookup"><span data-stu-id="c299a-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c299a-564">См. также</span><span class="sxs-lookup"><span data-stu-id="c299a-564">See also</span></span>
- [<span data-ttu-id="c299a-565">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c299a-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)

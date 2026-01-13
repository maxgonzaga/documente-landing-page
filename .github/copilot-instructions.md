For each response generated, have the following context in mind:

This is a HR document processing tool.

## Workflow

1. User creates a batch of files.
2. For each file in the batch, a background process identifies the document types present in the file and splits the file into one or more documents.
3. A background process extracts fields from each document. The list of fields to be extracted depends on the document type. Common fields:
    - CPF,
    - employee name,
    - employee number,
    - date,
    - exam result.
4. A background process tries to match the extracted CPF with the employee's table. If a match is found, the document will be linked to this employee. Otherwise, a new row will be addeed to the table.

## Entities

Batch: represents a request to ingest one or more files.

RawFile: represents a raw file extracted from an ingestion.

ParsedDocument: represents a document parsed from a RawFile.

Employee: represents an employee, which may have multiple linked documents.

Fields: represents a field extracted from a ParsedDocument. Each field has a name and a value.

## Relationships

One Batch can have many RawFiles.

One RawFile can have many Documents.

Each Document has fields.

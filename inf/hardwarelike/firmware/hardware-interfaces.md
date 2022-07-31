# hardware interfaces

ACPI  advanced configuration and power interface
ACPI is a low-level interface to the power hardware of the computer, allowing for power management; it is currently the standard for that purpose.
ACPI executes the requests it gets as bytecode, acting like black box, and thus presenting a built-in security risk.
The ACPI exposes its interface as ACPI tables.
The Windows Platform Binary Table is an ACPI tible that allows software to persist even beyond reinstalls.
The Superfish vulnerability was enabled by the Windows Platform Binary Table.
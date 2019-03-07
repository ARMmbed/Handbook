## Platform service

The Platform service introduces System Reset and [PSA Lifecycle](../lifecycle/psa-lifecycle.html) APIs.

The System Reset API enables a Non-Secure Processing Environment (NSPE) to request a system reset. The [Trusted Base System Architecture for M (TBSA-M)](https://pages.arm.com/psa-resources-tbsa-m.html) specification defines that power state must be managed by the Secure Processing Environment (SPE); therefore, the SPE carries out system reset after all critical tasks are completed.

### Platform service class reference

[![View code](https://www.mbed.com/embed/?type=library)](https://os.mbed.com/docs/development/mbed-os-api-doxy/lifecycle_8h.html)

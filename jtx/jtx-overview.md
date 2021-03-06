# JTX overview

_Jodd_ provides great, little, stand-alone transaction manager, _JTX_. It is a significant change in traditional thinking, since no \(j2ee\) application server is required; _JTX_ may be used in any Java code.

_JTX_ is built to be roughly similar to **JTA** up to certain point; but without complexity. It's goal is to works well with every-day web/desktop applications; not to manage heavy-weight requirements such as transactions across multiple domains, etc.

In a nutshell _JTX_ provides a transaction model that supports transaction demarcation over any number of resources - of any kind. Of course, the emphasis is put on database transactions; there is a layer built on top of _JTX_ to integrate it well with _Db_ and _Proxetta_ frameworks. _JTX_ may be used programmatically through simple API or declaratively using annotations.

### JTX in action

A picture is worth a thousand words, a good code example even more;\) Here is one real-life example how _JTX_ is used declaratively.

```java
    ...
    @Transaction
    public String view() {
        // read data db
        return result;
    }

    @ReadWriteTransaction
    public void store(int id) {
        // save data to db
    }

    @Transaction(propagation=PROPAGATION_REQUIRED, readOnly=false, timeout=100)
    public void update(int id) {
        // save data to db
    }
    ...
```

Cool, isn't it:\) This example already shows several _JTX_ features, like using custom annotations, but its definitely not the only way how _JTX_ can be used.

Following _JTX_ pages explains the concept behind the framework and its usage.


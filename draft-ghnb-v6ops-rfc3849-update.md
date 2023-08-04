---
title: Expanding the IPv6 Documentation Space
abbrev: Expanding the IPv6 Documentation Space
docname: draft-ghnb-v6ops-rfc3849-update-latest
v: 3
submissiontype: IETF
cat: std
ipr: trust200902
area: "Operations and Management"
wg: V6OPS
kw: Internet-Draft
updates: 3849

author:
      -
        ins: G. Huston
        name: Geoff Huston
        org: APNIC
        email: gih@apnic.net
      -
        ins: N. Buraglio
        name: Nick Buraglio
        org: Energy Sciences Network
        email: buraglio@forwardingplane.net

normative:
  RFC2119:
  RFC8200:
informative:
  RFC3849:

--- abstract

As the global deployment of IPv6 exapands and evolves, the need for larger, more flexible documentation address space has become a notable requirement for documenting larger, more complex deployments.

--- middle

# Introduction

{{RFC3849}} introduced 2001:db8::/32 describes the use of the IPv6
address prefix 2001:DB8::/32 as a reserved prefix for use in
documentation. With the rapid expansion of IPv6 production deployments since the assignment of this prefix, it has become increasingly obvious that a larger selection of reserved address space is required to address the ever-increasing sizes of RIR allocations.

# Current state

The largest assignments made to end users have been /19s. In the foreseeable future its unlikely that this will be repeated anytime soon, so a reservation of a /20 would cover documentation of the very largest of the known deployments.

~~~~~~~~~~
RIR IPV6 ALLOCATIONS
 number size
      4 /19
     24 /20
     13 /21
     36 /22
      7 /23
     64 /24
      9 /25
     18 /26
     22 /27
    168 /28
  15551 /29
    186 /30
    150 /31
  30530 /32
~~~~~~~~~~

# Conventions and Definitions

{::boilerplate bcp14-tagged}

# Security Considerations

TODO Security

# IANA Considerations

This document has no IANA actions.

--- back

# Acknowledgments
{:numbered="false"}

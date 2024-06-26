---
title: Expanding the IPv6 Documentation Space
abbrev: Expanding the IPv6 Documentation Space
docname: draft-ietf-v6ops-rfc3849-update-latest
v: 3
submissiontype: IETF
cat: info
ipr: trust200902
area: "Operations and Management"
wg: V6OPS
kw: Internet-Draft
pi: [toc, sortrefs, symrefs]
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
  IANAIPv6SPAR:
    target: https://www.iana.org/assignments/iana-ipv6-special-registry/iana-ipv6-special-registry.xhtml
    title: "IANA IPv6 Special-Purpose Address Registry"

informative:
  RFC3849:
  RFC4291:
  NROStatsReport:
    target: https://ftp.ripe.net/pub/stats/ripencc/nro-stats/latest/nro-delegated-stats
    title: "NRO Stats Report"
  BOGON:
    target: https://www.team-cymru.com/post/unravelling-the-mystery-of-bogons-a-senior-stakeholder-and-it-professional-guide
    title: "Team Cymru Bogon Guide"

--- abstract

The document describes the reservation of an additional IPv6 address prefix
for use in documentation. This update to RFC 3849 expands on the existing 2001:db8::/32
address block with the reservation of an additional, larger prefix.
The addition of a /20 allows documented examples to more closely reflect
a broader range of realistic, current deployment scenarios and more closely aligns with
contemporary allocation models for large networks.

--- middle

# Introduction

{{RFC3849}} introduced 2001:db8::/32, describing the use of the IPv6 address
prefix 2001:db8::/32 as a reserved prefix for use in documentation. The
rationale for this reservation was to reduce the likelihood of conflict and
confusion when relating documented examples to deployed systems.

As the global deployment of IPv6 expands and evolves, individual IPv6
network deployment scenarios have also increased is size and diversity, and
there is a requirement for documentation to reflect this increased diversity
and scope. The original 2001:db8::/32 reservation is inadequate to describe
many realistic current deployment scenarios.

Without this additional address allocation, documentation address prefixes
are drawn from address blocks already allocated or assigned to existing
organizations or to well known ISPs, or drawn from the currently unallocated
address pool. Such use conflicts with existing or future allocations or
assignments of IPv6 address space. The reservation of a further /20 IPv6
address prefix from the Global Unicast Address pool {{RFC4291}} for
documentation purposes avoids such conflicts.

# Current Assignment and Allocation Data

According to the allocation and assignment data published by the Regional
Internet Registries,
{{NROStatsReport}},
in August 2023 some 25.9% of all 62,770 recorded IPv6 unicast allocations and
assignments are larger than a /32 in size. The most common allocation or
assignment size is a /29, used in 24.8% of cases.

The four largest assignments made to end users have been /19s, but these
allocations were made before the RIRs' address allocation policies moved
away from the use of a fixed /48 site address prefix IPv6 address assignment
policies, and in the foreseeable future its unlikely that individual
networks require more than a /20. It is believed that a reservation of a /20
would cover the documentation needs as they relate the broad range of
realistic network deployments.

# Filtering and appropriate use

Documentation prefixes are for the use or relaying configuration and documentation examples and as such
MUST NOT be used for actual traffic, MUST NOT be  globally advertised, and SHOULD NOT be used internally for routed production traffic or other connectivity.
Documentation prefixes should be considered bogon and filtered in routing advertisements as appropriate.


# Conventions and Definitions

None.

# Security Considerations

This special use prefix should be marked as and considered {{BOGON}}. As is appropriate with bogon prefixes,
packets whose src/dst belongs to this prefix should be dropped and disallowed over the public Internet.

# IANA Considerations

IANA is to record the reservation of TBD::/20 in the IANA IPv6 Special-Purpose Address Registry;
{{IANAIPv6SPAR}}. The Source, Destination, Forwardable,
Globally Reachable and Reserved-by-Protocol fields should be recorded as
False. There is no Termination Date for this entry.
The name of the reservation is “Documentation".

--- back

# Acknowledgments
{:numbered="false"}
The authors would like to acknowledge the valuable input from XiPeng Xiao, Chris Cummings, Russ White, Kevin Myers, Ed Horley, Tom Coffeen, and Scott Hogg.

>[!note]
>Can be implemented with [[Blockchain]], but it is not obrigatory

>[!important]
>Implemented with [walt.id](https://walt.id/identity-infrastructure)

>[!warning]
>It is not similar to [[OAuth]]

# Patterns to Apply this Principles

- [[Decentralized Identifiers]]
- [[Verifiable Credentials]]

# Benefits

- User-centric data
	- Patient is the owner of the data
	- Right to be forgotten (RTBF)
- "Anonymized"
- User exposes only the requested data
- Explicit authorizations to use the data

# Challenges
- Revocate a Issue



# [[Self Sovereign Identity]] General Model

![[Self Sovereign Identity 2024-07-08 21.42.50.excalidraw|100%]]

# 10 Principles

1. **Existence.** <u>_Users must have an independent existence._</u> Any self-sovereign identity is ultimately based on the ineffable “I” that’s at the heart of identity. It can never exist wholly in digital form. This must be the kernel of self that is upheld and supported. A self-sovereign identity simply makes public and accessible some limited aspects of the “I” that already exists.
2. **Control.** <u>_Users must control their identities._</u> Subject to well-understood and secure algorithms that ensure the continued validity of an identity and its claims, the user is the ultimate authority on their identity. They should always be able to refer to it, update it, or even hide it. They must be able to choose celebrity or privacy as they prefer. This doesn’t mean that a user controls all of the claims on their identity: other users may make claims about a user, but they should not be central to the identity itself.
3. **Access.** <u>_Users must have access to their own data._</u> A user must always be able to easily retrieve all the claims and other data within his identity. There must be no hidden data and no gatekeepers. This does not mean that a user can necessarily modify all the claims associated with his identity, but it does mean they should be aware of them. It also does not mean that users have equal access to others’ data, only to their own.
4. **Transparency**. _Systems and algorithms must be transparent._ The systems used to administer and operate a network of identities must be open, both in how they function and in how they are managed and updated. The algorithms should be free, open-source, well-known, and as independent as possible of any particular architecture; anyone should be able to examine how they work.
5. **Persistence.** _Identities must be long-lived._ Preferably, identities should last forever, or at least for as long as the user wishes. Though private keys might need to be rotated and data might need to be changed, the identity remains. In the fast-moving world of the Internet, this goal may not be entirely reasonable, so at the least identities should last until they’ve been outdated by newer identity systems. This must not contradict a “right to be forgotten”; a user should be able to dispose of an identity if he wishes and claims should be modified or removed as appropriate over time. To do this requires a firm separation between an identity and its claims: they can't be tied forever.
6. **Portability.** _Information and services about identity must be transportable._ Identities must not be held by a singular third-party entity, even if it's a trusted entity that is expected to work in the best interest of the user. The problem is that entities can disappear — and on the Internet, most eventually do. Regimes may change, users may move to different jurisdictions. Transportable identities ensure that the user remains in control of his identity no matter what, and can also improve an identity’s persistence over time.
7. **Interoperability.** _Identities should be as widely usable as possible._ Identities are of little value if they only work in limited niches. The goal of a 21st-century digital identity system is to make identity information widely available, crossing international boundaries to create global identities, without losing user control. Thanks to persistence and autonomy these widely available identities can then become continually available.
8. **Consent.** _Users must agree to the use of their identity._ Any identity system is built around sharing that identity and its claims, and an interoperable system increases the amount of sharing that occurs. However, sharing of data must only occur with the consent of the user. Though other users such as an employer, a credit bureau, or a friend might present claims, the user must still offer consent for them to become valid. Note that this consent might not be interactive, but it must still be deliberate and well-understood.
9. **Minimalization.** _Disclosure of claims must be minimized._ When data is disclosed, that disclosure should involve the minimum amount of data necessary to accomplish the task at hand. For example, if only a minimum age is called for, then the exact age should not be disclosed, and if only an age is requested, then the more precise date of birth should not be disclosed. This principle can be supported with selective disclosure, range proofs, and other zero-knowledge techniques, but non-correlatibility is still a very hard (perhaps impossible) task; the best we can do is to use minimalization to support privacy as best as possible.
10. **Protection.** _The rights of users must be protected._ When there is a conflict between the needs of the identity network and the rights of individual users, then the network should err on the side of preserving the freedoms and rights of the individuals over the needs of the network. To ensure this, identity authentication must occur through independent algorithms that are censorship-resistant and force-resilient and that are run in a decentralized manner.
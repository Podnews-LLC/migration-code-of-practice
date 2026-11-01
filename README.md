# The migration code of practice
This is a suggested code of practice for podcast hosting companies who offer migration/copies/imports of podcasts from another podcast host. A simple set of promises, ideally to be "owned" by an industry body such as the Podcast Standards Project or similar.

This document is deliberately low-level, and intended to give as little friction to podcast hosting companies to import shows in the course of winning business. It is intended to ensure that podcast directories aren't deluged with illicit copies of copyrighted material, particularly those that are designed to earn money from existing podcasts.

## When a podcast is imported into your service:
* Respect the `podcast:locked` tag: do not import a podcast until the original creator removes an existing "lock".
* Support the `podcast:locked` tag in your own hosting service.
* Ensure that the original creator is made aware of the import taking place. At a bare minimum, send an email to the address in the feed if there is one, alerting them that a user has started a migration process and giving them a contact.

## Wait for the redirect before making money
The way that a podcast migration is achieved is a 30x redirect from the old RSS feed to the new one. This requires the specific permission of the original owner of the podcast. This acts as an identity check. Therefore:
* Do not allow any monetisation to take place until a redirect has been confirmed. Dynamically inserted audio is fine for testing; but no money may be made by publisher or host until a redirect has been confirmed.
* Do not allow one-click distribution to Apple/Spotify/etc until a redirect has been confirmed. (Ideally, your UX should stop a duplicate submission to these directories).
* 
_Redirects are normally possible from all reputable podcast hosts. However, where a redirect is not possible, a 404 error (the original feed going away) may also be acceptable._

## Other things to consider:
While not part of the code of practice, there are a few other things for a successful redirect for your client:
* Ensure no broken links: the main `link` of the podcast is likely to point to the old podcast hosting company's show page. If it does, it should be changed accordingly.
* Retain the `podcast:guid` and the individual episode `guid` elements, to ensure that podcast apps don't treat these episodes as brand new.


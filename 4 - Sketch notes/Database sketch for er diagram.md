# Sketch note: 2026-03-02 14:57

# Database sketch for er diagram

## Senter (dragvoll, moholt, etc)
- [ ] id
- [ ] navn
- [ ] addresse
- [ ] fasiliteter
- [ ] åpeningstider
- [ ] saler
- [ ] bemanning (med tid)

## Sal
- [ ] id
- [ ] sykler

## Tredemølle
- [ ] Produsent
- [ ] Max hastighet
- [ ] Max stigning
- [ ] nummer
- [ ] sted

## Sykler
- [ ] BodyBike
- [ ] nummer
- [ ] sted

## Gruppetimer
- [ ] id
- [ ] starttid og slutttid
- [ ] antall plasser
- [ ] opprette dato
- [ ] aktivitet (type gruppetime kun merket med "spin")
- [ ] instruktør
- [ ] meldt på

## Bruker
- [ ] id
- [ ] prikk relasjon
- [ ] fornavn
- [ ] etternavn
- [ ] epost
- [ ] mobilnr

## Instructor for
- [ ] brukerId
- [ ] GruppetimeId

## Registered for
- [ ] brukerId
- [ ] GruppetimeId
- [ ] timestamp

## Attended
- [ ] brukerId
- [ ] GruppetimeId
- [ ] attended

## Idrettslag
- [ ] id
- [ ] navn

## SalBooking
- [ ] idrettslagId
- [ ] salId
- [ ] tidspunkt

## StudentIdrettslag medlem
- [ ] idrettslagId
- [ ] BrukerId


---
layout: essay
type: essay
title: "Final Project Idea -- Manoa Matching"
date: 2025-04-01
published: false
labels:
  - Software Engineering
  - Nextjs
---

## Overview
**Problem:** Despite 20,000 students on the UH Manoa campus, some students may have a hard time making friends outside of their (ongoing/previous) classes or majors. For freshmen and sophomores, this could be due to being in a completely new environment; juniors and seniors may not have the time to commit to social events, find it difficult to meet classmates outside of their current major, or have a hard time breaking into pre-existing friend groups. By developing friendships outside of a specific major, students can meet new perspectives, network to find prospective career paths, and find unique experiences in UH Manoa.

**Solution:** To facilitate student connection, we introduce **Manoa Matching**, a social networking app that applies matching functionalities reminiscent of dating apps (_Tinder_, _Hinge_, etc.) but in the context of finding friends on the UH Manoa campus. 

**Authored by:** Codie Nakamura, Chaezen-Lee Pebria, Aaron Ramos, Masaki Sakai

## Approach
After creating an account, users can approve or skip profiles randomly shown to them. These profiles will likely contain a name, image(s), and relevant information placed during account creation. When two users approve each other’s profiles, they are given the opportunity to chat with each other on a separate page. 

Users can access a ‘Friends List’ page to favorite, block, or delete existing friends. Another important page would be a user ‘Profile Page’ where various profile details (including photos) can be edited.

## Mockup Page Ideas
* Landing page
* User home page
* User profile page
* "Matching" page 
* Friends page
* Chat page 
* Settings page

Here are tentative descriptions of certain pages:

**User Profile:** Add/edit name, photo(s), major, likes/interests, list of (previous/current) classes, dorm/commuter/other status, clubs, MBTI

**Matching:** Random person pops up and users have the option of “match” or “skip” with two buttons

**Friends:** Add freinds to a favorites/block list that can also be accessed; this page also includes the feature to delete friends

**Chat:** List of chats with people matched and a selected chat page that allows for message functioning

**Settings:** Settings to filter people shown (i.e. by major, interests, etc.)

## Use Case Ideas
* User goes to landing page, signs up, completes account creation process (adds their name, photo(s), major, likes/interests, list of (previous/current) classes, dorm/commuter/other status, clubs, MBTI)
* After creating profile, user is brought to matching page and intuitively learns to "match"/"skip" on profiles shown to them
* If 2 users “match” on each other’s profiles, they are added to each others’ ‘Friends List’ page
* When new friends are added, users are given a notification that leads them into the chat page
* _Best case:_ Users chat with each other and become friends
* _Worst case:_ After some chats, a user decides to delete/block the other

## Beyond the Basics
- Show mutual friends on profile
- Pathing compatibility (GIS), consider students who may constantly cross paths due to classes
- Campus event suggestions for people of the same interest to attend
# Universe.sql
New project
--
-- PostgreSQL database dump
--

-- Dumped from database version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)
-- Dumped by pg_dump version 12.9 (Ubuntu 12.9-2.pgdg20.04+1)

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

DROP DATABASE universe;
--
-- Name: universe; Type: DATABASE; Schema: -; Owner: freecodecamp
--

CREATE DATABASE universe WITH TEMPLATE = template0 ENCODING = 'UTF8' LC_COLLATE = 'C.UTF-8' LC_CTYPE = 'C.UTF-8';


ALTER DATABASE universe OWNER TO freecodecamp;

\connect universe

SET statement_timeout = 0;
SET lock_timeout = 0;
SET idle_in_transaction_session_timeout = 0;
SET client_encoding = 'UTF8';
SET standard_conforming_strings = on;
SELECT pg_catalog.set_config('search_path', '', false);
SET check_function_bodies = false;
SET xmloption = content;
SET client_min_messages = warning;
SET row_security = off;

SET default_tablespace = '';

SET default_table_access_method = heap;

--
-- Name: comet; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.comet (
    comet_id integer NOT NULL,
    comet_type text,
    comet_discription text,
    comet_weight numeric(4,1) NOT NULL,
    comet_age integer NOT NULL,
    name character varying(30)
);


ALTER TABLE public.comet OWNER TO freecodecamp;

--
-- Name: comet_comet_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.comet_comet_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.comet_comet_id_seq OWNER TO freecodecamp;

--
-- Name: comet_comet_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.comet_comet_id_seq OWNED BY public.comet.comet_id;


--
-- Name: galaxy; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.galaxy (
    galaxy_id integer NOT NULL,
    name character varying(30),
    galaxy_size integer NOT NULL,
    galaxy_discription text,
    has_life boolean,
    star_id integer NOT NULL
);


ALTER TABLE public.galaxy OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_galaxy_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_galaxy_id_seq OWNER TO freecodecamp;

--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_galaxy_id_seq OWNED BY public.galaxy.galaxy_id;


--
-- Name: galaxy_star_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.galaxy_star_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.galaxy_star_id_seq OWNER TO freecodecamp;

--
-- Name: galaxy_star_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.galaxy_star_id_seq OWNED BY public.galaxy.star_id;


--
-- Name: moon; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.moon (
    moon_id integer NOT NULL,
    name character varying(30),
    moon_discription text,
    planet_id integer NOT NULL,
    moon_stage integer,
    moon_age integer
);


ALTER TABLE public.moon OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.moon_moon_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.moon_moon_id_seq OWNER TO freecodecamp;

--
-- Name: moon_moon_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.moon_moon_id_seq OWNED BY public.moon.moon_id;


--
-- Name: planet; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.planet (
    planet_id integer NOT NULL,
    name character varying(30),
    planet_weight numeric(4,2) NOT NULL,
    planet_discription text,
    has_life boolean,
    is_spherical boolean,
    star_id integer NOT NULL
);


ALTER TABLE public.planet OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.planet_planet_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.planet_planet_id_seq OWNER TO freecodecamp;

--
-- Name: planet_planet_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.planet_planet_id_seq OWNED BY public.planet.planet_id;


--
-- Name: star; Type: TABLE; Schema: public; Owner: freecodecamp
--

CREATE TABLE public.star (
    star_id integer NOT NULL,
    name character varying(30),
    stars_size integer NOT NULL,
    star_weight numeric(4,2),
    star_discription text,
    has_life boolean,
    galaxy_id integer NOT NULL
);


ALTER TABLE public.star OWNER TO freecodecamp;

--
-- Name: star_galaxy_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_galaxy_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_galaxy_id_seq OWNER TO freecodecamp;

--
-- Name: star_galaxy_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_galaxy_id_seq OWNED BY public.star.galaxy_id;


--
-- Name: star_star_id_seq; Type: SEQUENCE; Schema: public; Owner: freecodecamp
--

CREATE SEQUENCE public.star_star_id_seq
    AS integer
    START WITH 1
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 1;


ALTER TABLE public.star_star_id_seq OWNER TO freecodecamp;

--
-- Name: star_star_id_seq; Type: SEQUENCE OWNED BY; Schema: public; Owner: freecodecamp
--

ALTER SEQUENCE public.star_star_id_seq OWNED BY public.star.star_id;


--
-- Name: comet comet_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.comet ALTER COLUMN comet_id SET DEFAULT nextval('public.comet_comet_id_seq'::regclass);


--
-- Name: galaxy galaxy_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN galaxy_id SET DEFAULT nextval('public.galaxy_galaxy_id_seq'::regclass);


--
-- Name: galaxy star_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy ALTER COLUMN star_id SET DEFAULT nextval('public.galaxy_star_id_seq'::regclass);


--
-- Name: moon moon_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon ALTER COLUMN moon_id SET DEFAULT nextval('public.moon_moon_id_seq'::regclass);


--
-- Name: planet planet_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet ALTER COLUMN planet_id SET DEFAULT nextval('public.planet_planet_id_seq'::regclass);


--
-- Name: star star_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN star_id SET DEFAULT nextval('public.star_star_id_seq'::regclass);


--
-- Name: star galaxy_id; Type: DEFAULT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star ALTER COLUMN galaxy_id SET DEFAULT nextval('public.star_galaxy_id_seq'::regclass);


--
-- Data for Name: comet; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.comet VALUES (1, 'small', 'really beautiful', 43.5, 55, 'Holmes');
INSERT INTO public.comet VALUES (2, 'big', 'very nice', 79.3, 34, 'Encke');
INSERT INTO public.comet VALUES (3, 'tiny', 'attractive', 22.8, 67, 'Donati');
INSERT INTO public.comet VALUES (4, 'little', 'appealing', 76.1, 11, 'Alma');
INSERT INTO public.comet VALUES (5, 'large', 'bright', 3.7, 7, 'Roxy');


--
-- Data for Name: galaxy; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.galaxy VALUES (2, 'Cigar', 874122, 'bright', false, 2);
INSERT INTO public.galaxy VALUES (3, 'Pinwheel', 783210, 'charming', false, 3);
INSERT INTO public.galaxy VALUES (4, 'Andromeda', 4389021, 'appealing', false, 4);
INSERT INTO public.galaxy VALUES (5, 'Black EYE', 48329021, 'unforgettable', true, 5);
INSERT INTO public.galaxy VALUES (6, 'Milky Way', 76432, 'engaging', true, 6);
INSERT INTO public.galaxy VALUES (7, 'Tadpole', 8832194, 'huge', true, 7);


--
-- Data for Name: moon; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.moon VALUES (24, 'waxing gibbous Moon', 'nice', 2, 3, 2);
INSERT INTO public.moon VALUES (25, 'full Moon', 'very large', 1, 4, 2);
INSERT INTO public.moon VALUES (26, 'waning gibbous Moon', 'appealing', 1, 7, 3);
INSERT INTO public.moon VALUES (27, 'last quater Moon', 'little', 2, 6, 3);
INSERT INTO public.moon VALUES (1, 'new Moon', 'tiny', 4, 2, 2);
INSERT INTO public.moon VALUES (2, 'waxig crescent Moon', 'extremely small', 4, 1, 4);
INSERT INTO public.moon VALUES (3, 'first quater Moon', 'really small', 5, 5, 8);
INSERT INTO public.moon VALUES (28, 'new Moon', 'fresh', 12, 8, 4);
INSERT INTO public.moon VALUES (29, 'cool Moon', 'engaging', 11, 9, 4);
INSERT INTO public.moon VALUES (30, 'second Moon', 'nothing special', 7, 10, 8);
INSERT INTO public.moon VALUES (31, 'final Moon', 'old', 6, 13, 1);
INSERT INTO public.moon VALUES (32, 'last Moon', 'unforgettable', 10, 12, 7);
INSERT INTO public.moon VALUES (33, 'second Moon', 'specific', 10, 11, 2);
INSERT INTO public.moon VALUES (34, 'My Moon', 'the best one ever', 5, 14, 3);
INSERT INTO public.moon VALUES (35, 'First Moon', 'particular', 7, 15, 12);
INSERT INTO public.moon VALUES (36, 'Spring Moon', 'lovely', 8, 16, 10);
INSERT INTO public.moon VALUES (37, 'Winter Moon', 'sad', 10, 17, 12);
INSERT INTO public.moon VALUES (38, 'great Moon', 'tremendous', 10, 18, 9);
INSERT INTO public.moon VALUES (39, 'third Moon', 'old', 9, 19, 5);
INSERT INTO public.moon VALUES (40, 'Summer Moon', 'extremely beautiful', 5, 20, 11);


--
-- Data for Name: planet; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.planet VALUES (1, 'Mercury', 25.40, 'very beautiful', true, true, 2);
INSERT INTO public.planet VALUES (2, 'Venus', 27.30, 'extremely attractive', false, true, 3);
INSERT INTO public.planet VALUES (4, 'Earth', 44.50, 'the best one', true, true, 4);
INSERT INTO public.planet VALUES (5, 'Jupiter', 61.43, 'engaging', false, false, 3);
INSERT INTO public.planet VALUES (6, 'Uranus', 9.45, 'tremendous', false, false, 6);
INSERT INTO public.planet VALUES (7, 'Mars', 61.73, 'great', true, true, 7);
INSERT INTO public.planet VALUES (8, 'Neptune', 81.20, 'really specific', false, true, 4);
INSERT INTO public.planet VALUES (9, 'Saturn', 37.12, 'attractive', true, true, 7);
INSERT INTO public.planet VALUES (10, 'SUN', 64.57, 'warm', false, false, 5);
INSERT INTO public.planet VALUES (11, 'Sun', 83.33, 'extremely hot', true, false, 3);
INSERT INTO public.planet VALUES (12, 'My planet', 5.27, 'really cool', true, true, 4);
INSERT INTO public.planet VALUES (14, 'New', 38.20, 'strange', true, true, 2);


--
-- Data for Name: star; Type: TABLE DATA; Schema: public; Owner: freecodecamp
--

INSERT INTO public.star VALUES (2, 'Sun', 121234, 32.53, 'very beautiful', false, 2);
INSERT INTO public.star VALUES (3, 'ALTAIR', 32198, 25.12, 'unysual', false, 3);
INSERT INTO public.star VALUES (4, 'Vega', 47602, 11.20, 'attractive', true, 4);
INSERT INTO public.star VALUES (5, 'Procyon', 12702, 23.67, 'new', true, 5);
INSERT INTO public.star VALUES (6, 'Rigel', 5672, 56.40, 'great', true, 6);
INSERT INTO public.star VALUES (7, 'Chara', 8962, 32.50, 'huge', false, 7);


--
-- Name: comet_comet_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.comet_comet_id_seq', 5, true);


--
-- Name: galaxy_galaxy_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_galaxy_id_seq', 7, true);


--
-- Name: galaxy_star_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.galaxy_star_id_seq', 7, true);


--
-- Name: moon_moon_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.moon_moon_id_seq', 40, true);


--
-- Name: planet_planet_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.planet_planet_id_seq', 14, true);


--
-- Name: star_galaxy_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_galaxy_id_seq', 7, true);


--
-- Name: star_star_id_seq; Type: SEQUENCE SET; Schema: public; Owner: freecodecamp
--

SELECT pg_catalog.setval('public.star_star_id_seq', 7, true);


--
-- Name: comet comet_comet_age_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.comet
    ADD CONSTRAINT comet_comet_age_key UNIQUE (comet_age);


--
-- Name: comet comet_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.comet
    ADD CONSTRAINT comet_pkey PRIMARY KEY (comet_id);


--
-- Name: galaxy galaxy_galaxy_size_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_galaxy_size_key UNIQUE (galaxy_size);


--
-- Name: galaxy galaxy_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.galaxy
    ADD CONSTRAINT galaxy_pkey PRIMARY KEY (galaxy_id);


--
-- Name: moon moon_moon_stage_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_moon_stage_key UNIQUE (moon_stage);


--
-- Name: moon moon_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_pkey PRIMARY KEY (moon_id);


--
-- Name: planet planet_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_pkey PRIMARY KEY (planet_id);


--
-- Name: planet planet_planet_id_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_planet_id_key UNIQUE (planet_id);


--
-- Name: star star_pkey; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_pkey PRIMARY KEY (star_id);


--
-- Name: star star_stars_size_key; Type: CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_stars_size_key UNIQUE (stars_size);


--
-- Name: moon moon_planet_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.moon
    ADD CONSTRAINT moon_planet_id_fkey FOREIGN KEY (planet_id) REFERENCES public.planet(planet_id);


--
-- Name: planet planet_star_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.planet
    ADD CONSTRAINT planet_star_id_fkey FOREIGN KEY (star_id) REFERENCES public.star(star_id);


--
-- Name: star star_galaxy_id_fkey; Type: FK CONSTRAINT; Schema: public; Owner: freecodecamp
--

ALTER TABLE ONLY public.star
    ADD CONSTRAINT star_galaxy_id_fkey FOREIGN KEY (galaxy_id) REFERENCES public.galaxy(galaxy_id);


--
-- PostgreSQL database dump complete
--

